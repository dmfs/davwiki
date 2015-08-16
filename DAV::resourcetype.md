<!-- --- title: DAV::resourcetype -->
<!-- --- link_title: DAV:resourcetype -->
<!-- --- current_spec: RFC 4918 -->
<!-- --- current_spec_rfc_number: 4918 -->
<!-- --- current_spec_rfc_section: 15.9 -->
<!-- --- xml_namespace: DAV: -->
<!-- --- xml_element: resourcetype -->
<!-- --- type: property -->
<!-- --- purpose: Specifies the nature of the resource. -->
<!-- --- value: a list of elements representing resource types  -->
<!-- --- protected: SHOULD -->
<!-- --- allprop: MUST -->
<!-- --- valid_for: MUST be defined on all DAV-compliant resources. -->

<!-- >>> property-summary-box --><!-- <<< -->

<!-- below is a list of common sections for property definitions. Adjust the list as needed. Don't forget to block-quote any text that's copied from the RFC -->

###Purpose
>Specifies the nature of the resource.

###Protected
>SHOULD be protected. Resource type is generally decided
>through the operation creating the resource ([[MKCOL]] vs [[PUT]]), not by
>[[PROPPATCH]].

###COPY/MOVE behavior
>Generally a COPY/MOVE of a resource results in
>the same type of resource at the destination.

###Description
>MUST be defined on all DAV-compliant resources.  Each
>child element identifies a specific type the resource belongs to,
>such as '[[DAV::collection]]', which is the only resource type defined by
>this specification (see [RFC 4918, Section 14.3](http://tools.ietf.org/html/rfc4918#section-14.3)).
>If the element contains
>the '[[DAV::collection]]' child element plus additional unrecognized
>elements, it should generally be treated as a collection.  If the
>element contains no recognized child elements, it should be
>treated as a non-collection resource.  The default value is empty.
>This element MUST NOT contain text or mixed content.  Any custom
>child element is considered to be an identifier for a resource
>type.

###Example
>(fictional example to show extensibility)
>
```xml
   <x:resourcetype xmlns:x="DAV:">
       <x:collection/>
       <f:search-results xmlns:f="http://www.example.com/ns"/>
   </x:resourcetype>
```

### DTD
[[RFC 4918]] doesn't specify a DTD, but the examples and the description imply the following:

```
<!ELEMENT resourcetype ANY >
```

Valid child elements are elements that represent a resource type.
Known resource types are:

* [[DAV::collection]]
* [[urn:ietf:params:xml:ns:caldav:calendar]]
* [[urn:ietf:params:xml:ns:carddav:addressbook]].
