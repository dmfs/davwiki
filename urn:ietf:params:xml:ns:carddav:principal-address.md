<!-- --- title: urn:ietf:params:xml:ns:carddav:principal-address -->
<!-- --- link_title: CARDDAV:principal-address -->
<!-- --- current_spec: RFC 6352 -->
<!-- --- current_spec_rfc_number: 6352 -->
<!-- --- current_spec_rfc_section: 7.1.2 -->
<!-- --- xml_namespace: urn:ietf:params:xml:ns:carddav -->
<!-- --- xml_element: principal-address -->
<!-- --- type: property -->
<!-- --- purpose: Identifies the URL of an address object resource that corresponds to the user represented by the principal. -->
<!-- --- value: a single [[DAV:href|DAV::href]] element -->
<!-- --- protected: MAY -->
<!-- --- allprop: SHOULD NOT -->
<!-- --- valid_for: [[DAV:principal|DAV::principal]] -->

<!-- >>> property-summary-box --><!-- <<< -->

<!-- below is a list of common sections for property definitions. Adjust the list as needed. Don't forget to block-quote any text that's copied from the RFC -->

###Purpose
> Identifies the URL of an address object resource that corresponds to the user represented by the principal.

###Protected
> MAY be protected if the server provides a fixed location for principal addresses.

###COPY/MOVE behavior
> This property value MUST be preserved in [[COPY]] and [[MOVE]] operations.

###Allprop behavior
> SHOULD NOT be returned by a [[PROPFIND]] [[DAV:allprop]] request.

###Description
> The CARDDAV:principal-address property is meant to allow users to easily find contact information for users represented by principals on the system. This property specifies the URL of the resource containing the corresponding contact information. The resource could be an address object resource in  an address book collection, or it could be a resource in a "regular" collection.

### DTD
> 
```
<!ELEMENT principal-address (DAV:href)>
```

###Example
> 
>
```xml
<C:principal-address xmlns:D="DAV:"
  xmlns:C="urn:ietf:params:xml:ns:carddav">
  <D:href>/system/cyrus.vcf</D:href>
</C:principal-address>
```
