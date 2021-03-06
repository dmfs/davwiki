<!-- --- title: urn:ietf:params:xml:ns:carddav:max-resource-size -->
<!-- --- link_title: CARDDAV:max-resource-size -->
<!-- --- current_spec: RFC 6352 -->
<!-- --- current_spec_rfc_number: 6352 -->
<!-- --- current_spec_rfc_section: 6.2.3 -->
<!-- --- xml_namespace: urn:ietf:params:xml:ns:carddav -->
<!-- --- xml_element: max-resource-size -->
<!-- --- type: property -->
<!-- --- purpose: Provides a numeric value indicating the maximum size in octets of a resource that the server is willing to accept when an address object resource is stored in an address book collection. -->
<!-- --- value: any text representing a numeric value-->
<!-- --- protected: MUST -->
<!-- --- allprop: SHOULD NOT -->
<!-- --- valid_for: [[urn:ietf:params:xml:ns:carddav:addressbook]] -->

<!-- >>> property-summary-box --><!-- <<< -->

<!-- below is a list of common sections for property definitions. Adjust the list as needed. Don't forget to block-quote any text that's copied from the RFC -->

Note: this XML element has ambiguous definitions, see below.

###Purpose
> Provides a numeric value indicating the maximum size in octets of a resource that the server is willing to accept when an address object resource is stored in an address book collection.

###Value
> Any text representing a numeric value.

###Protected
> MUST be protected as it indicates limits provided by the server.

###COPY/MOVE behavior
> This property value MUST be preserved in [[COPY]] and [[MOVE]] operations.

###Allprop behavior
> SHOULD NOT be returned by a [[PROPFIND]] [[DAV:allprop]] request.

###Description
> The CARDDAV:max-resource-size is used to specify a numeric value that represents the maximum size in octets that the server is willing to accept when an address object resource is stored in an address book collection. Any attempt to store an address book object resource exceeding this size MUST result in an error, with the CARDDAV:max-resource-size precondition ([Section 6.3.2.1](https://tools.ietf.org/html/rfc6352#section-6.3.2.1)) being violated. In the absence of this property, the client can assume that the server will allow storing a resource of any reasonable size.

### DTD
> 
```
<!ELEMENT max-resource-size (#PCDATA)>
<!-- PCDATA value: a numeric value (positive decimal integer) -->
```

###Example
> 
>
```xml
<C:max-resource-size xmlns:C="urn:ietf:params:xml:ns:carddav"
>102400</C:max-resource-size>
```

### XML element ambiguity

This element has been defined twice with different meanings:

* In the context of a request or [[multistatus|DAV::multistatus]] element it represents a property as defined in [Section 6.2.3](http://tools.ietf.org/html/rfc6352#section-6.2.3)
* In the context of an error response it represents a [[precondition]] as specified in [Section 6.3.2.1](https://tools.ietf.org/html/rfc6352#section-6.3.2.1):

>(CARDDAV:max-resource-size): The resource submitted in the [[PUT]] request, or targeted by a [[COPY]] or [[MOVE]] request, MUST have a size in octets less than or equal to the value of the CARDDAV:max-resource-size property value ([Section 6.2.3](http://tools.ietf.org/html/rfc6352#section-6.2.3)) on the address book collection where the resource will be stored.

