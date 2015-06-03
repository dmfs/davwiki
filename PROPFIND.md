<!-- --- title: PROPFIND Method -->

[[_TOC_]]

<div id="summary-box" markdown="1">
###Summary

#####Specification
[[RFC 4918]]
[Section 9.1](http://tools.ietf.org/html/rfc4918#section-9.1).

#####Request root element
[[DAV::propfind]]

#####Request properties
[[Cacheable|Cacheable Method]], [[Idempotent|Idempotent Method]], [[Safe|Safe Method]]
 
#####Valid success status codes
[[207]]

</div>

###Description
> The PROPFIND method retrieves properties defined on the resource
> identified by the Request-URI, if the resource does not have any
> internal members, or on the resource identified by the Request-URI
> and potentially its member resources, if the resource is a collection
> that has internal member URLs.  All DAV-compliant resources MUST
> support the PROPFIND method and the [[DAV::propfind]] XML element
> ([Section 14.20](http://tools.ietf.org/html/rfc4918#section-14.20)) along with all XML elements defined for use with that
> element.

> A client MUST submit a Depth header with a value of "0", "1", or
> "infinity" with a PROPFIND request.  Servers MUST support "0" and "1"
> depth requests on WebDAV-compliant resources and SHOULD support
> "infinity" requests.  In practice, support for infinite-depth
> requests MAY be disabled, due to the performance and security
> concerns associated with this behavior.  Servers SHOULD treat a
> request without a [[Depth header]] as if a "Depth: infinity" header was
> included.

> A client may submit a 'propfind' XML element in the body of the
> request method describing what information is being requested.  It is
> possible to:
>
> *  Request particular property values, by naming the properties
>    desired within the 'prop' element (the ordering of properties in
>    here MAY be ignored by the server),
> *  Request property values for those properties defined in this
>    specification (at a minimum) plus dead properties, by using the
>    'allprop' element (the 'include' element can be used with
>    'allprop' to instruct the server to also include additional live
>    properties that may not have been returned otherwise),
> *  Request a list of names of all the properties defined on the
>    resource, by using the 'propname' element.
>
> A client may choose not to submit a request body.  An empty PROPFIND
> request body MUST be treated as if it were an 'allprop' request.
>
> Note that 'allprop' does not return values for all live properties.
> WebDAV servers increasingly have expensively-calculated or lengthy
> properties (see [[RFC 3253]] and [[RFC 3744]]) and do not return all
> properties already.  Instead, WebDAV clients can use [[DAV::propname]]
> requests to discover what live properties exist, and request named
> properties when retrieving values.  For a live property defined
> elsewhere, that definition can specify whether or not that live
> property would be returned in 'allprop' requests.
>
> All servers MUST support returning a response of content type text/
> xml or application/xml that contains a [[DAV::multistatus]] XML element that
> describes the results of the attempts to retrieve the various
> properties.
>
> If there is an error retrieving a property, then a proper error
> result MUST be included in the response.  A request to retrieve the
> value of a property that does not exist is an error and MUST be noted
> with a 'response' XML element that contains a [[404 (Not Found)|404]] status
> value.
>
> Consequently, the '[[DAV::multistatus]]' XML element for a collection resource
> MUST include a '[[DAV::response]]' XML element for each member URL of the
> collection, to whatever depth was requested.  It SHOULD NOT include
> any '[[DAV::response]]' elements for resources that are not WebDAV-compliant.
> Each '[[DAV::response]]' element MUST contain an '[[DAV::href]]' element that contains
> the URL of the resource on which the properties in the prop XML
> element are defined.  Results for a PROPFIND on a collection resource
> are returned as a flat list whose order of entries is not
> significant.  Note that a resource may have only one value for a
> property of a given name, so the property may only show up once in
> PROPFIND responses.
>
> Properties may be subject to access control.  In the case of
> 'allprop' and 'propname' requests, if a principal does not have the
> right to know whether a particular property exists, then the property
> MAY be silently excluded from the response.
>
> Some PROPFIND results MAY be cached, with care, as there is no cache
> validation mechanism for most properties.  This method is both [[safe|Safe Method]]
> and [[idempotent|Idempotent Method]] (see [Section 9.1 of RFC2616](http://tools.ietf.org/html/rfc2616#section-9.1)).

###PROPFIND Status Codes

> This section, as with similar sections for other methods, provides
> some guidance on error codes and preconditions or postconditions
> (defined in [Section 16](http://tools.ietf.org/html/rfc4918#section-16)) that might be particularly useful with
> PROPFIND.
>
> [[403 Forbidden|403]] - A server MAY reject PROPFIND requests on collections
> with depth header of "Infinity", in which case it SHOULD use this
> error with the precondition code '[[DAV::propfind-finite-depth]]' inside the
> error body.

###Status Codes for Use in 'propstat' Element

> In PROPFIND responses, information about individual properties is
> returned inside 'propstat' elements (see Section 14.22), each
> containing an individual 'status' element containing information
> about the properties appearing in it.  The list below summarizes the
> most common status codes used inside 'propstat'; however, clients
> should be prepared to handle other 2/3/4/5xx series status codes as
> well.
>
> 200 OK - A property exists and/or its value is successfully returned.
>
> 401 Unauthorized - The property cannot be viewed without appropriate
> authorization.
>
> 403 Forbidden - The property cannot be viewed regardless of
> authentication.
>
> 404 Not Found - The property does not exist.

###Examples

####Retrieving Named Properties

#####Request
>
```
PROPFIND /file HTTP/1.1
Host: www.example.com
Content-type: application/xml; charset="utf-8"
Content-Length: xxxx

<?xml version="1.0" encoding="utf-8" ?>
<D:propfind xmlns:D="DAV:">
  <D:prop xmlns:R="http://ns.example.com/boxschema/">
    <R:bigbox/>
    <R:author/>
    <R:DingALing/>
    <R:Random/>
  </D:prop>
</D:propfind>
```

#####Response
>
```
HTTP/1.1 207 Multi-Status
Content-Type: application/xml; charset="utf-8"
Content-Length: xxxx

<?xml version="1.0" encoding="utf-8" ?>
<D:multistatus xmlns:D="DAV:">
  <D:response xmlns:R="http://ns.example.com/boxschema/">
    <D:href>http://www.example.com/file</D:href>
    <D:propstat>
      <D:prop>
        <R:bigbox>
          <R:BoxType>Box type A</R:BoxType>
        </R:bigbox>
        <R:author>
          <R:Name>J.J. Johnson</R:Name>
        </R:author>
      </D:prop>
      <D:status>HTTP/1.1 200 OK</D:status>
    </D:propstat>
    <D:propstat>
      <D:prop><R:DingALing/><R:Random/></D:prop>
      <D:status>HTTP/1.1 403 Forbidden</D:status>
      <D:responsedescription> The user does not have access to the
 DingALing property.
      </D:responsedescription>
    </D:propstat>
  </D:response>
  <D:responsedescription> There has been an access violation error.
  </D:responsedescription>
</D:multistatus>
```

> In this example, PROPFIND is executed on a non-collection resource
> http://www.example.com/file.  The propfind XML element specifies the
> name of four properties whose values are being requested.  In this
> case, only two properties were returned, since the principal issuing
> the request did not have sufficient access rights to see the third
> and fourth properties.

####Using 'propname' to Retrieve All Property Names

#####Request
>
```xml
     PROPFIND /container/ HTTP/1.1
     Host: www.example.com
     Content-Type: application/xml; charset="utf-8"
     Content-Length: xxxx

     <?xml version="1.0" encoding="utf-8" ?>
     <propfind xmlns="DAV:">
       <propname/>
     </propfind>
```

#####Response
>
```xml
HTTP/1.1 207 Multi-Status
Content-Type: application/xml; charset="utf-8"
Content-Length: xxxx

<?xml version="1.0" encoding="utf-8" ?>
<multistatus xmlns="DAV:">
  <response>
    <href>http://www.example.com/container/</href>
    <propstat>
      <prop xmlns:R="http://ns.example.com/boxschema/">
        <R:bigbox/>
        <R:author/>
        <creationdate/>
        <displayname/>
        <resourcetype/>
        <supportedlock/>
      </prop>
      <status>HTTP/1.1 200 OK</status>
    </propstat>
  </response>
  <response>
    <href>http://www.example.com/container/front.html</href>
    <propstat>
      <prop xmlns:R="http://ns.example.com/boxschema/">
        <R:bigbox/>
        <creationdate/>
        <displayname/>
        <getcontentlength/>
        <getcontenttype/>
        <getetag/>
        <getlastmodified/>
        <resourcetype/>
        <supportedlock/>
      </prop>
      <status>HTTP/1.1 200 OK</status>
    </propstat>
  </response>
</multistatus>
```

> In this example, PROPFIND is invoked on the collection resource
> http://www.example.com/container/, with a propfind XML element
> containing the propname XML element, meaning the name of all
> properties should be returned.  Since no Depth header is present, it
> assumes its default value of "infinity", meaning the name of the
> properties on the collection and all its descendants should be
> returned.
>
> Consistent with the previous example, resource
> http://www.example.com/container/ has six properties defined on it:
> bigbox and author in the "http://ns.example.com/boxschema/"
> namespace, and creationdate, displayname, resourcetype, and
> supportedlock in the "DAV:" namespace.
>
> The resource http://www.example.com/container/index.html, a member of
> the "container" collection, has nine properties defined on it, bigbox
> in the "http://ns.example.com/boxschema/" namespace and creationdate,
> displayname, getcontentlength, getcontenttype, getetag,
> getlastmodified, resourcetype, and supportedlock in the "DAV:"
> namespace.
>
> This example also demonstrates the use of XML namespace scoping and
> the default namespace.  Since the "xmlns" attribute does not contain
> a prefix, the namespace applies by default to all enclosed elements.
> Hence, all elements that do not explicitly state the namespace to
> which they belong are members of the "DAV:" namespace.

####Using So-called 'allprop'

> Note that 'allprop', despite its name, which remains for backward-
> compatibility, does not return every property, but only dead
> properties and the live properties defined in this specification.

#####Request
>
```xml
PROPFIND /container/ HTTP/1.1
Host: www.example.com
Depth: 1
Content-Type: application/xml; charset="utf-8"
Content-Length: xxxx

<?xml version="1.0" encoding="utf-8" ?>
<D:propfind xmlns:D="DAV:">
  <D:allprop/>
</D:propfind>
```

#####Response
>
```xml
HTTP/1.1 207 Multi-Status
Content-Type: application/xml; charset="utf-8"
Content-Length: xxxx

<?xml version="1.0" encoding="utf-8" ?>
<D:multistatus xmlns:D="DAV:">
  <D:response>
    <D:href>/container/</D:href>
    <D:propstat>
      <D:prop xmlns:R="http://ns.example.com/boxschema/">
        <R:bigbox><R:BoxType>Box type A</R:BoxType></R:bigbox>
        <R:author><R:Name>Hadrian</R:Name></R:author>
        <D:creationdate>1997-12-01T17:42:21-08:00</D:creationdate>
        <D:displayname>Example collection</D:displayname>
        <D:resourcetype><D:collection/></D:resourcetype>
        <D:supportedlock>
          <D:lockentry>
            <D:lockscope><D:exclusive/></D:lockscope>
            <D:locktype><D:write/></D:locktype>
          </D:lockentry>
          <D:lockentry>
            <D:lockscope><D:shared/></D:lockscope>
            <D:locktype><D:write/></D:locktype>
          </D:lockentry>
        </D:supportedlock>
      </D:prop>
      <D:status>HTTP/1.1 200 OK</D:status>
    </D:propstat>
  </D:response>
  <D:response>
    <D:href>/container/front.html</D:href>
    <D:propstat>
      <D:prop xmlns:R="http://ns.example.com/boxschema/">
        <R:bigbox><R:BoxType>Box type B</R:BoxType>
        </R:bigbox>
        <D:creationdate>1997-12-01T18:27:21-08:00</D:creationdate>
        <D:displayname>Example HTML resource</D:displayname>
        <D:getcontentlength>4525</D:getcontentlength>
        <D:getcontenttype>text/html</D:getcontenttype>
        <D:getetag>"zzyzx"</D:getetag>
        <D:getlastmodified
          >Mon, 12 Jan 1998 09:25:56 GMT</D:getlastmodified>
        <D:resourcetype/>
        <D:supportedlock>
          <D:lockentry>
            <D:lockscope><D:exclusive/></D:lockscope>
            <D:locktype><D:write/></D:locktype>
          </D:lockentry>
          <D:lockentry>
            <D:lockscope><D:shared/></D:lockscope>
            <D:locktype><D:write/></D:locktype>
          </D:lockentry>
        </D:supportedlock>
      </D:prop>
      <D:status>HTTP/1.1 200 OK</D:status>
    </D:propstat>
  </D:response>
</D:multistatus>
```
> In this example, PROPFIND was invoked on the resource
> http://www.example.com/container/ with a Depth header of 1, meaning
> the request applies to the resource and its children, and a propfind
> XML element containing the allprop XML element, meaning the request
> should return the name and value of all the dead properties defined
> on the resources, plus the name and value of all the properties
> defined in this specification.  This example illustrates the use of
> relative references in the 'href' elements of the response.
>
> The resource http://www.example.com/container/ has six properties
> defined on it: 'bigbox' and 'author in the
> "http://ns.example.com/boxschema/" namespace, DAV:creationdate, DAV:
> displayname, DAV:resourcetype, and DAV:supportedlock.
>
> The last four properties are WebDAV-specific, defined in Section 15.
> Since GET is not supported on this resource, the get* properties
> (e.g., DAV:getcontentlength) are not defined on this resource.  The
> WebDAV-specific properties assert that "container" was created on
> December 1, 1997, at 5:42:21PM, in a time zone 8 hours west of GMT
> (DAV:creationdate), has a name of "Example collection" (DAV:
> displayname), a collection resource type (DAV:resourcetype), and
> supports exclusive write and shared write locks (DAV:supportedlock).
>
> The resource http://www.example.com/container/front.html has nine
> properties defined on it:
>
> 'bigbox' in the "http://ns.example.com/boxschema/" namespace (another
> instance of the "bigbox" property type), [[DAV::creationdate]], [[DAV::displayname]], [[DAV::getcontentlength]], [[DAV::getcontenttype]], [[DAV::getetag]],
> [[DAV::getlastmodified]], [[DAV::resourcetype]], and [[DAV::supportedlock]].
>
> The DAV-specific properties assert that "front.html" was created on
> December 1, 1997, at 6:27:21PM, in a time zone 8 hours west of GMT
> ([[DAV::creationdate]]), has a name of "Example HTML resource" (DAV:
> displayname), a content length of 4525 bytes ([[DAV::getcontentlength]]),
> a MIME type of "text/html" ([[DAV::getcontenttype]]), an entity tag of
> "zzyzx" ([[DAV::getetag]]), was last modified on Monday, January 12, 1998,
> at 09:25:56 GMT ([[DAV::getlastmodified]]), has an empty resource type,
> meaning that it is not a collection ([[DAV::resourcetype]]), and supports
> both exclusive write and shared write locks ([[DAV::supportedlock]]).

####Using 'allprop' with 'include'

#####Request
>
```xml
PROPFIND /mycol/ HTTP/1.1
Host: www.example.com
Depth: 1
Content-Type: application/xml; charset="utf-8"
Content-Length: xxxx

<?xml version="1.0" encoding="utf-8" ?>
<D:propfind xmlns:D="DAV:">
  <D:allprop/>
  <D:include>
    <D:supported-live-property-set/>
    <D:supported-report-set/>
  </D:include>
</D:propfind>
```
>
> In this example, PROPFIND is executed on the resource
> http://www.example.com/mycol/ and its internal member resources.  The
> client requests the values of all live properties defined in this
> specification, plus all dead properties, plus two more live
> properties defined in [[RFC 3253]].  The response is not shown.

