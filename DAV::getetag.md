<!-- --- title: DAV::getetag -->
<!-- --- link_title: DAV:getetag -->
<!-- --- current_spec: RFC 4918 -->
<!-- --- current_spec_rfc_number: 4918 -->
<!-- --- current_spec_rfc_section: 15.6 -->
<!-- --- xml_namespace: DAV: -->
<!-- --- xml_element: getetag -->
<!-- --- type: property -->
<!-- --- purpose: Contains the [[ETag]] header value as it would be returned by a [[GET]] without accept headers. -->
<!-- --- value: entity-tag -->
<!-- --- protected: MUST -->
<!-- --- allprop: MUST -->
<!-- --- valid_for: any DAV-compliant resource that returns the [[Etag header|headers/Etag]] -->

<!-- >>> property-summary-box --><!-- <<< -->

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

