<!-- --- title: urn:ietf:params:xml:ns:caldav:max-instances -->
<!-- --- link_title: CALDAV:max-instances -->
<!-- --- current_spec: RFC 4791 -->
<!-- --- current_spec_rfc_number: 4791 -->
<!-- --- current_spec_rfc_section: 5.2.8 -->
<!-- --- xml_namespace: urn:ietf:params:xml:ns:caldav -->
<!-- --- xml_element: max-instances -->
<!-- --- type: property -->
<!-- --- purpose: Provides a numeric value indicating the maximum number of recurrence instances that a calendar object resource stored in a calendar collection can generate. -->
<!-- --- value: A numeric value (integer greater than zero) -->
<!-- --- protected: MUST -->
<!-- --- allprop: SHOULD NOT -->
<!-- --- valid_for: [[urn:ietf:params:xml:ns:caldav:calendar]] -->

<!-- >>> property-summary-box --><!-- <<< -->

<!-- below is a list of common sections for property definitions. Adjust the list as needed. Don't forget to block-quote any text that's copied from the RFC -->

###Purpose
> Provides a numeric value indicating the maximum number of recurrence instances that a calendar object resource stored in a calendar collection can generate.

###Value
A numeric value (integer greater than zero)

###Conformance
> This property MAY be defined on any [[calendar collection|urn:ietf:params:xml:ns:caldav:calendar]]. If defined, it MUST be protected and SHOULD NOT be returned by a [[PROPFIND]] [[DAV::allprop]] request (as defined in [Section 12.14.1 of RFC 2518](https://tools.ietf.org/html/rfc2518#section-12.14.1)).

###Description
> The CALDAV:max-instances is used to specify a numeric value that indicates the maximum number of recurrence instances that a calendar object resource stored in a calendar collection can generate. Any attempt to store a calendar object resource with a recurrence pattern that generates more instances than this value MUST result in an error, with the CALDAV:max-instances precondition ([Section 5.3.2.1](https://tools.ietf.org/html/rfc4791#section-5.3.2.1)) being violated. In the absence of this property, the client can assume that the server has no limits on the number of recurrence instances it can handle or expand.

### DTD
> 
```
<!ELEMENT  max-instances (#PCDATA)>
PCDATA value: a numeric value (integer greater than zero)
```

###Example
> 
>
```xml
<C:max-instances xmlns:C="urn:ietf:params:xml:ns:caldav"
    >100</C:max-instances>
```
