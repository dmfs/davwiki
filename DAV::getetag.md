<!-- --- title: DAV::getetag -->

<div id="summary-box" markdown="1">
###Summary

#####Specification
[[RFC 4918]]
[Section 15.6](http://tools.ietf.org/html/rfc4918#section-15.6).

#####Type
Property

#####Protected
MUST

#####Returned by allprop
MUST

#####Compliance
Valid and required on all DAV-compliant resources that return an [[ETag]] header.
</div>

###Purpose
> Contains the [[ETag]] header value (from [Section 14.19 of RFC 2616](http://tools.ietf.org/html/rfc2616#section-14.19)) as it would be returned by a [[GET]] without accept headers.

###Protected
>MUST be protected because this value is created and controlled by the server.

###COPY/MOVE behavior
>This property value is dependent on the final state of the destination resource, not the value of the property on the source resource.  Also note the considerations in [Section 8.8](http://tools.ietf.org/html/rfc4918#section-8.8).

###Description
>The getetag property MUST be defined on any DAV-compliant resource that returns the Etag header.  Refer to [Section 3.11 of RFC 2616](http://tools.ietf.org/html/rfc2616#section-3.11) for a complete definition of the semantics of an ETag, and to [Section 8.6](http://tools.ietf.org/html/rfc4918#section-8.6) for a discussion of ETags in WebDAV.

Note that an ETag MUST be quoted and MUST NOT contain any double quote characters itself, see [RFC 7232, Section 2.3](https://tools.ietf.org/html/rfc7232#section-2.3).


### DTD
>
```
   <!ELEMENT getetag (#PCDATA) >
```