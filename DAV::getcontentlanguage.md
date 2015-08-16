<!-- --- title: DAV::getcontentlanguage -->
<!-- --- link_title: DAV:getcontentlanguage -->
<!-- --- current_spec: RFC 4918 -->
<!-- --- current_spec_rfc_number: 4918 -->
<!-- --- current_spec_rfc_section: 15.3 -->
<!-- --- xml_namespace: DAV: -->
<!-- --- xml_element: getcontentlanguage -->
<!-- --- type: property -->
<!-- --- purpose: Contains the Content-Language header value as it would be returned by a [[GET]] without accept headers. -->
<!-- --- value: language-tag -->
<!-- --- protected: SHOULD NOT -->
<!-- --- allprop: MUST -->
<!-- --- valid_for: any DAV-compliant resource that returns the [[Content-Language header|headers/Content-Language]] on a [[GET]] -->

<!-- >>> property-summary-box --><!-- <<< -->

<!-- below is a list of common sections for property definitions. Adjust the list as needed. Don't forget to block-quote any text that's copied from the RFC -->

###Purpose
> Contains the Content-Language header value (from [Section 14.12 of RFC 2616](http://tools.ietf.org/html/rfc2616#section-14.12)) as it would be returned by a [[GET]] without accept headers.

###Value
> language-tag (language-tag is defined in [Section 3.10 of RFC 2616](http://tools.ietf.org/html/rfc2616#section-3.10))

###Protected
> SHOULD NOT be protected, so that clients can reset the language. Note that servers implementing [[RFC 2518]] might have made this a protected property as this is a new requirement.

###COPY/MOVE behavior
> This property value SHOULD be preserved in COPY and MOVE operations.

###Description
> The DAV:getcontentlanguage property MUST be defined on any DAV-compliant resource that returns the [[Content-Language header|headers/Content-Language]] on a [[GET]].

### DTD
> 
```
<!ELEMENT getcontentlanguage (#PCDATA) >

```
