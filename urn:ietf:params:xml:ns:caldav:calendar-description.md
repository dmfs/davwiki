<!-- --- title: urn:ietf:params:xml:ns:caldav:calendar-description -->
<!-- --- link_title: CALDAV:calendar-description-->
<!-- --- current_spec: RFC 4791 -->
<!-- --- current_spec_rfc_number: 4791 -->
<!-- --- current_spec_rfc_section: 5.2.1 -->
<!-- --- xml_namespace: urn:ietf:params:xml:ns:caldav -->
<!-- --- xml_element: calendar-description -->
<!-- --- type: property -->
<!-- --- purpose: Provides a human-readable description of the calendar collection. -->
<!-- --- value: any text -->
<!-- --- protected: MAY -->
<!-- --- allprop: SHOULD NOT -->
<!-- --- valid_for: [[urn:ietf:params:xml:ns:caldav:calendar]] -->

<!-- >>> property-summary-box --><!-- <<< -->

<!-- below is a list of common sections for property definitions. Adjust the list as needed. Don't forget to block-quote any text that's copied from the RFC -->

###Purpose
> Provides a human-readable description of the calendar collection.

###Value
String

###Conformance
> This property MAY be defined on any [[calendar collection|urn:ietf:params:xml:ns:caldav:calendar]]. If defined, it MAY be protected and SHOULD NOT be returned by a [[PROPFIND]] [[DAV::allprop]] request (as defined in [Section 12.14.1 of RFC 2518](https://tools.ietf.org/html/rfc2518#section-12.14.1)). An [[xml:lang]] attribute indicating the human language of the description SHOULD be set for this property by clients or through server provisioning.  Servers MUST return any [[xml:lang]] attribute if set for the property.

###Description
>  If present, the property contains a description of the calendar collection that is suitable for presentation to a user. If not present, the client should assume no description for the calendar collection.

### DTD
> 
```
<!ELEMENT calendar-description (#PCDATA)>
PCDATA value: string
```

###Example
> 
>
```xml
<C:calendar-description xml:lang="fr-CA"
    xmlns:C="urn:ietf:params:xml:ns:caldav"
>Calendrier de Mathilde Desruisseaux</C:calendar-description>
```
