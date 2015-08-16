<!-- --- title: urn:ietf:params:xml:ns:carddav:supported-address-data -->
<!-- --- link_title: CARDDAV:supported-address-data -->
<!-- --- current_spec: RFC 6352 -->
<!-- --- current_spec_rfc_number: 6352 -->
<!-- --- current_spec_rfc_section: 6.2.2 -->
<!-- --- xml_namespace: urn:ietf:params:xml:ns:carddav -->
<!-- --- xml_element: supported-address-data -->
<!-- --- type: property -->
<!-- --- purpose: Specifies what media types are allowed for address object resources in an address book collection. -->
<!-- --- value: list of [[CARDDAV:address-data-type|urn:ietf:params:xml:ns:carddav:address-data-type]]-->
<!-- --- protected: MUST -->
<!-- --- allprop: SHOULD NOT -->
<!-- --- valid_for: [[urn:ietf:params:xml:ns:carddav:addressbook]] -->

<!-- >>> property-summary-box --><!-- <<< -->

<!-- below is a list of common sections for property definitions. Adjust the list as needed. Don't forget to block-quote any text that's copied from the RFC -->

###Purpose
> Specifies what media types are allowed for address object resources in an address book collection.

###Protected
> MUST be protected as it indicates the level of support provided by the server.

###COPY/MOVE behavior
> This property value MUST be preserved in [[COPY]] and [[MOVE]] operations.

###Allprop behavior
> SHOULD NOT be returned by a [[PROPFIND]] [[DAV:allprop]] request.

###Description
> The CARDDAV:supported-address-data property is used to  specify the media type supported for the address object resources contained in a given address book collection (e.g., vCard version 3.0). Any attempt by the client to store address object resources with a media type not listed in this property MUST result in an error, with the CARDDAV:supported-address-data precondition ([Section 6.3.2.1](https://tools.ietf.org/html/rfc6352#section-6.3.2.1)) being violated. In the absence of this property, the server MUST only accept data with the media type "text/vcard" and vCard version 3.0, and clients can assume that is all the server will accept.

### DTD
> 
```
<!ELEMENT supported-address-data (address-data-type+)>

<!ELEMENT address-data-type EMPTY>
<!ATTLIST address-data-type content-type CDATA "text/vcard"
                     version CDATA "3.0">
<!-- content-type value: a MIME media type -->
<!-- version value: a version string -->
```

###Example
> 
>
```xml
<C:supported-address-data
  xmlns:C="urn:ietf:params:xml:ns:carddav">
 <C:address-data-type content-type="text/vcard" version="3.0"/>
</C:supported-address-data>
```
