<!-- --- title: DAV::getetag -->

<div id="summary-box" markdown="1">
<h4>Summary</h4>

<dl>
<dt>Specification</dt>
<dd markdown="1">[[RFC 4918]]
[Section 15.6](http://tools.ietf.org/html/rfc4918#section-15.6)
</dd>
<dt>Type</dt>
<dd markdown="1">Property
</dd>
<dt>Protected</dt>
<dd markdown="1">MUST 
</dd>
<dt>Returned by allprop</dt>
<dd markdown="1">MUST 
</dd>
<dt>Valid for resource types</dt>
<dd markdown="1">any DAV-compliant resource that returns the [[Etag header|headers/Etag]]
</dd>
</dl>

</div>

<!-- below is a list of common sections for property definitions. Adjust the list as needed. Don't forget to block-quote any text that's copied from the RFC -->

###Purpose
> Contains the [[ETag]] header value (from [Section 14.19 of RFC 2616](http://tools.ietf.org/html/rfc2616#section-14.19)) as it would be returned by a [[GET]] without accept headers.

### Value
> entity-tag (defined in [Section 3.11 of RFC2616](http://tools.ietf.org/html/rfc2616#section-3.11))

###Protected
>MUST be protected because this value is created and controlled by the server.

###COPY/MOVE behavior
>This property value is dependent on the final state of the destination resource, not the value of the property on the source resource.  Also note the considerations in [Section 8.8](http://tools.ietf.org/html/rfc4918#section-8.8).

###Description
>The getetag property MUST be defined on any DAV-compliant resource that returns the [[Etag header|headers/Etag]].  Refer to [Section 3.11 of RFC 2616](http://tools.ietf.org/html/rfc2616#section-3.11) for a complete definition of the semantics of an ETag, and to [Section 8.6](http://tools.ietf.org/html/rfc4918#section-8.6) for a discussion of ETags in WebDAV.

Note that an ETag MUST be quoted and MUST NOT contain any double quote characters itself, see [RFC 7232, Section 2.3](https://tools.ietf.org/html/rfc7232#section-2.3).


### DTD
>
```
   <!ELEMENT getetag (#PCDATA) >
```
