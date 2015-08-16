<!-- --- title: DAV::getcontentlength -->
<!-- --- link_title: DAV:getcontentlength -->
<!-- --- current_spec: RFC 4918 -->
<!-- --- current_spec_rfc_number: 4918 -->
<!-- --- current_spec_rfc_section: 15.4 -->
<!-- --- xml_namespace: DAV: -->
<!-- --- xml_element: getcontentlength -->
<!-- --- type: property -->
<!-- --- purpose: Contains the Content-Length header returned by a [[GET]] without accept headers. -->
<!-- --- value: non-negative decimal number -->
<!-- --- protected: MUST -->
<!-- --- allprop: MUST -->
<!-- --- valid_for: any DAV-compliant resource that returns the [[Content-Length header|headers/Content-Lenght]] in response to a [[GET]] -->

<!-- >>> property-summary-box --><!-- <<< -->

<!-- below is a list of common sections for property definitions. Adjust the list as needed. Don't forget to block-quote any text that's copied from the RFC -->

###Purpose
> Contains the Content-Length header returned by a [[GET]] without accept headers.

###Value
> See [Section 14.13 of RFC 2616](http://tools.ietf.org/html/rfc2616#section-14.13)

###Protected
> This property is computed, therefore protected.

###COPY/MOVE behavior
> This property value is dependent on the size of the destination resource, not the value of the property on the source resource.

###Description
> The DAV:getcontentlength property MUST be defined on any DAV-compliant resource that returns the [[Content-Length header|headers/Content-Lenght]] in response to a [[GET]].

### DTD
> 
```
<!ELEMENT getcontentlength (#PCDATA) >

```
