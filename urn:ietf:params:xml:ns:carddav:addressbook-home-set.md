<!-- --- title: urn:ietf:params:xml:ns:carddav:addressbook-home-set -->
<!-- --- link_title: CARDDAV:addressbook-home-set -->
<!-- --- current_spec: RFC 6352 -->
<!-- --- current_spec_rfc_number: 6352 -->
<!-- --- current_spec_rfc_section: 7.1.1 -->
<!-- --- xml_namespace: urn:ietf:params:xml:ns:carddav -->
<!-- --- xml_element: addressbook-home-set -->
<!-- --- type: property -->
<!-- --- purpose: Identifies the URL of any WebDAV collections that contain address book collections owned by the associated principal resource. -->
<!-- --- value: a list of [[DAV:href|DAV::href]] elements -->
<!-- --- protected: MAY -->
<!-- --- allprop: SHOULD NOT -->
<!-- --- valid_for: [[DAV:principal|DAV::principal]] -->

<!-- >>> property-summary-box --><!-- <<< -->

<!-- below is a list of common sections for property definitions. Adjust the list as needed. Don't forget to block-quote any text that's copied from the RFC -->

###Purpose
> Identifies the URL of any WebDAV collections that contain address book collections owned by the associated principal resource.

###Protected
> MAY be protected if the server has fixed locations in which address books are created.

###COPY/MOVE behavior
> This property value MUST be preserved in [[COPY]] and [[MOVE]] operations.

###Allprop behavior
> SHOULD NOT be returned by a [[PROPFIND]] [[DAV:allprop]] request.

###Description
> The CARDDAV:addressbook-home-set property is meant to allow users to easily find the address book collections owned by the principal. Typically, users will group all the address book collections that they own under a common collection. This property specifies the URL of collections that are either address book collections or ordinary collections that have child or descendant address book collections owned by the principal.

### DTD
> 
```
<!ELEMENT addressbook-home-set (DAV:href*)>
```

###Example
> 
>
```xml
<C:addressbook-home-set xmlns:D="DAV:"
  xmlns:C="urn:ietf:params:xml:ns:carddav">
 <D:href>/bernard/addresses/</D:href>
</C:addressbook-home-set>
```

