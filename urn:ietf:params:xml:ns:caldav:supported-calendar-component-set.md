<!-- --- title: urn:ietf:params:xml:ns:caldav:supported-calendar-component-set -->
<!-- --- link_title: CALDAV:supported-calendar-component-set -->
<!-- --- current_spec: RFC 4791 -->
<!-- --- current_spec_rfc_number: 4791 -->
<!-- --- current_spec_rfc_section: 5.2.3 -->
<!-- --- xml_namespace: urn:ietf:params:xml:ns:caldav -->
<!-- --- xml_element: supported-calendar-component-set -->
<!-- --- type: property -->
<!-- --- purpose: Specifies the calendar component types (e.g., VEVENT, VTODO, etc.) that calendar object resources can contain in the calendar collection. -->
<!-- --- value: a non-empty list of [[CALDAV:comp|urn:ietf:params:xml:ns:caldav:comp]] elements -->
<!-- --- protected: MUST -->
<!-- --- allprop: SHOULD NOT -->
<!-- --- valid_for: [[urn:ietf:params:xml:ns:caldav:calendar]] -->

<!-- >>> property-summary-box --><!-- <<< -->

<!-- below is a list of common sections for property definitions. Adjust the list as needed. Don't forget to block-quote any text that's copied from the RFC -->

###Purpose
> Specifies the calendar component types (e.g., VEVENT, VTODO, etc.) that calendar object resources can contain in the calendar collection.

###Conformance
> This property MAY be defined on any [[calendar collection|urn:ietf:params:xml:ns:caldav:calendar]]. If defined, it MUST be protected and SHOULD NOT be returned by a [[PROPFIND]] [[DAV::allprop]] request (as defined in [Section 12.14.1 of RFC 2518](https://tools.ietf.org/html/rfc2518#section-12.14.1)).

###Description
> The CALDAV:supported-calendar-component-set property is used to specify restrictions on the calendar component types that calendar object resources may contain in a calendar collection. Any attempt by the client to store calendar object resources with component types not listed in this property, if it exists, MUST result in an error, with the CALDAV:supported-calendar-component precondition ([Section 5.3.2.1](https://tools.ietf.org/html/rfc4791#section-5.3.2.1)) being violated. Since this property is protected, it cannot be changed by clients using a [[PROPPATCH]] request.  However, clients can initialize the value of this property when creating a new calendar collection with [[MKCALENDAR]]. The empty-element tag <C:comp name="VTIMEZONE"/> MUST only be specified if support for calendar object resources that only contain VTIMEZONE components is provided or desired. Support for VTIMEZONE components in calendar object resources that contain VEVENT or VTODO components is always assumed. In the absence of this property, the server MUST accept all component types, and the client can assume that all component types are accepted.

### DTD
> 
```
<!ELEMENT supported-calendar-component-set (comp+)>
```

###Example
> 
>
```xml
<C:supported-calendar-component-set
     xmlns:C="urn:ietf:params:xml:ns:caldav">
   <C:comp name="VEVENT"/>
   <C:comp name="VTODO"/>
 </C:supported-calendar-component-set>
```
