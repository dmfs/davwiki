<!-- --- title: urn:ietf:params:xml:ns:carddav:addressbook-description -->
<!-- --- link_title: CARDDAV:addressbook-description -->
<!-- --- current_spec: RFC 6352 -->
<!-- --- current_spec_rfc_number: 6352 -->
<!-- --- current_spec_rfc_section: 6.2.1 -->
<!-- --- xml_namespace: urn:ietf:params:xml:ns:carddav -->
<!-- --- xml_element: addressbook-description -->
<!-- --- type: property -->
<!-- --- purpose: Provides a human-readable description of the address book collection. -->
<!-- --- value: any text-->
<!-- --- protected: SHOULD NOT -->
<!-- --- allprop: SHOULD NOT -->
<!-- --- valid_for: [[urn:ietf:params:xml:ns:carddav:addressbook]] -->

<!-- >>> property-summary-box --><!-- <<< -->

<!-- below is a list of common sections for property definitions. Adjust the list as needed. Don't forget to block-quote any text that's copied from the RFC -->

###Purpose
> Provides a human-readable description of the address book collection.

###Value
> Any text.

###Protected
> SHOULD NOT be protected so that users can specify a description.

###COPY/MOVE behavior
> This property value SHOULD be preserved in [[COPY]] and [[MOVE]] operations.

###Allprop behavior
> SHOULD NOT be returned by a [[PROPFIND]] [[DAV:allprop]] request.

###Description
> This property contains a description of the address book collection that is suitable for presentation to a user. The [[xml:lang]] attribute can be used to add a language tag for the value of this property.

### DTD
> 
```
<!ELEMENT addressbook-description (#PCDATA)>
<!-- PCDATA value: string -->
```

###Example
> 
>
```xml
<C:addressbook-description xml:lang="fr-CA"
  xmlns:C="urn:ietf:params:xml:ns:carddav"
>Adresses de Oliver Daboo</C:addressbook-description>
```

