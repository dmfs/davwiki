<!-- --- title: DAV::getlastmodified -->
<!-- --- link_title: DAV:getlastmodified -->
<!-- --- current_spec: RFC 4918 -->
<!-- --- current_spec_rfc_number: 4918 -->
<!-- --- current_spec_rfc_section: 15.7 -->
<!-- --- xml_namespace: DAV: -->
<!-- --- xml_element: getlastmodified -->
<!-- --- type: property -->
<!-- --- purpose: Contains the [[Last-Modified header|headers/last-modified]] value as it would be returned by a GET method without accept headers. -->
<!-- --- value: rfc1123-date -->
<!-- --- protected: SHOULD -->
<!-- --- allprop: MUST -->
<!-- --- valid_for: any DAV-compliant resource that returns the [[Last-Modified header|headers/Last-Modified]] -->

<!-- >>> property-summary-box --><!-- <<< -->

<!-- below is a list of common sections for property definitions. Adjust the list as needed. Don't forget to block-quote any text that's copied from the RFC -->

###Purpose
> Contains the Last-Modified header value (from [Section 14.29 of RFC 2616](http://tools.ietf.org/html/rfc2616#section-14.29)) as it would be returned by a GET method without accept headers.

###Value
> rfc1123-date (defined in [Section 3.3.1 of RFC 2616](http://tools.ietf.org/html/rfc2616#section-3.3.1))

###Protected
> SHOULD be protected because some clients may rely on the value for appropriate caching behavior, or on the value of the Last-Modified header to which this property is linked.

###COPY/MOVE behavior
>  This property value is dependent on the last modified date of the destination resource, not the value of the property on the source resource.  Note that some server implementations use the file system date modified value for the DAV:getlastmodified value, and this can be preserved in a MOVE      even when the HTTP Last-Modified value SHOULD change. Note that since [[RFC 2616]] requires clients to use ETags where provided, a server implementing ETags can count on clients using a much better mechanism than modification dates for offline synchronization or cache control.  Also note the considerations in [Section 8.8.](http://tools.ietf.org/html/rfc4918#section-8.8)

###Description
>  The last-modified date on a resource SHOULD only reflect changes in the body (the [[GET]] responses) of the resource. A change in a property only SHOULD NOT cause the last-modified date to change, because clients MAY rely on the last-modified date to know when to overwrite the existing body. The DAV:getlastmodified property MUST be defined on any DAV-compliant resource that returns the [[Last-Modified header|headers/Last-Modified]] in response to a [[GET]].

### DTD
> 
```
<!ELEMENT getlastmodified (#PCDATA) >
```
