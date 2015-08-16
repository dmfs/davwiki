<!-- --- title: urn:ietf:params:xml:ns:caldav:max-resource-size -->
<!-- --- link_title: CALDAV:max-resource-size -->
<!-- --- current_spec: RFC 4791 -->
<!-- --- current_spec_rfc_number: 4791 -->
<!-- --- current_spec_rfc_section: 5.2.5 -->
<!-- --- xml_namespace: urn:ietf:params:xml:ns:caldav -->
<!-- --- xml_element: max-resource-size -->
<!-- --- type: property -->
<!-- --- purpose: Provides a numeric value indicating the maximum size of a resource in octets that the server is willing to accept when a calendar object resource is stored in a calendar collection. -->
<!-- --- value: A numeric value (positive integer) -->
<!-- --- protected: MUST -->
<!-- --- allprop: SHOULD NOT -->
<!-- --- valid_for: [[urn:ietf:params:xml:ns:caldav:calendar]] -->

<!-- >>> property-summary-box --><!-- <<< -->

<!-- below is a list of common sections for property definitions. Adjust the list as needed. Don't forget to block-quote any text that's copied from the RFC -->

###Purpose
> Provides a numeric value indicating the maximum size of a resource in octets that the server is willing to accept when a calendar object resource is stored in a calendar collection.

###Value
A numeric value (positive integer)

###Conformance
> This property MAY be defined on any [[calendar collection|urn:ietf:params:xml:ns:caldav:calendar]]. If defined, it MUST be protected and SHOULD NOT be returned by a [[PROPFIND]] [[DAV::allprop]] request (as defined in [Section 12.14.1 of RFC 2518](https://tools.ietf.org/html/rfc2518#section-12.14.1)).

###Description
>  The CALDAV:max-resource-size is used to specify a numeric value that represents the maximum size in octets that the server is willing to accept when a calendar object resource is stored in a calendar collection. Any attempt to store a calendar object resource exceeding this size MUST result in an error, with the CALDAV:max-resource-size precondition ([Section 5.3.2.1](https://tools.ietf.org/html/rfc4791#section-5.3.2.1)) being violated. In the absence of this property, the client can assume that the server will allow storing a resource of any reasonable size.

### DTD
> 
```
<!ELEMENT max-resource-size (#PCDATA)>
PCDATA value: a numeric value (positive integer)
```

###Example
> 
>
```xml
<C:max-resource-size xmlns:C="urn:ietf:params:xml:ns:caldav"
>102400</C:max-resource-size>
```
