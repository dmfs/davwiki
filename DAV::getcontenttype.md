<!-- --- title: DAV::getcontenttype -->
<!-- --- link_title: DAV:getcontenttype -->
<!-- --- current_spec: RFC 4918 -->
<!-- --- current_spec_rfc_number: 4918 -->
<!-- --- current_spec_rfc_section: 15.5 -->
<!-- --- xml_namespace: DAV: -->
<!-- --- xml_element: getcontenttype -->
<!-- --- type: property -->
<!-- --- purpose: Contains the Content-Type header value as it would be returned by a [[GET]] without accept headers.-->
<!-- --- value: media-type -->
<!-- --- protected: MAY -->
<!-- --- allprop: MUST -->
<!-- --- valid_for: any DAV-compliant resource that returns the [[Content-Type header|headers/Content-Type]] in response to a [[GET]] -->

<!-- >>> property-summary-box --><!-- <<< -->

<!-- below is a list of common sections for property definitions. Adjust the list as needed. Don't forget to block-quote any text that's copied from the RFC -->

###Purpose
> Contains the Content-Type header value (from [Section 14.17 of RFC 2616](http://tools.ietf.org/html/rfc2616#section-14.17 )) as it would be returned by a [[GET]] without accept headers.

###Value
> media-type (defined in [Section 3.7 of RFC 2616](http://tools.ietf.org/html/rfc2616#section-3.7 ))

###Protected
> Potentially protected if the server prefers to assign content types on its own (see also discussion in [Section 9.7.1](http://tools.ietf.org/html/rfc4918#section-9.7.1))

###COPY/MOVE behavior
> This property value SHOULD be preserved in COPY and MOVE operations.

###Description
> This property MUST be defined on any DAV-compliant resource that returns the [[Content-Type header|headers/Content-Type]] in response to a [[GET]].

### DTD
> 
```
<!ELEMENT getcontenttype (#PCDATA) >
```
