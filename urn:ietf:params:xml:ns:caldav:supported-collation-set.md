<!-- --- title: urn:ietf:params:xml:ns:supported-collation-set -->
<!-- --- link_title: CALDAV:supported-collation-set -->
<!-- --- current_spec: RFC 4791 -->
<!-- --- current_spec_rfc_number: 4791 -->
<!-- --- current_spec_rfc_section: 7.5.1 -->
<!-- --- xml_namespace: urn:ietf:params:xml:ns:caldav -->
<!-- --- xml_element: supported-collation-set -->
<!-- --- type: property -->
<!-- --- purpose: Identifies the set of collations supported by the server for text matching operations. -->
<!-- --- value: a list of [[CALDAV:supported-collation|urn:ietf:params:xml:ns:caldav:supported-collation]] elements -->
<!-- --- protected: MUST -->
<!-- --- allprop: SHOULD NOT -->
<!-- --- valid_for: This property MUST be defined on any resource that supports a report that does text matching. -->

<!-- >>> property-summary-box --><!-- <<< -->

<!-- below is a list of common sections for property definitions. Adjust the list as needed. Don't forget to block-quote any text that's copied from the RFC -->

###Purpose
> Identifies the set of collations supported by the server for text matching operations.

###Conformance
> This property MUST be defined on any resource that supports a report that does text matching.  If defined, it MUST be protected and SHOULD NOT be returned by a [[PROPFIND]] [[DAV:allprop]] request (as defined in [Section 12.14.1 of RFC 2518](https://tools.ietf.org/html/rfc2518#section-12.14.1)).

###Description
> The CALDAV:supported-collation-set property contains zero or more [[CALDAV:supported-collation|urn:ietf:params:xml:ns:supported-collation]] elements, which specify the collection identifiers of the collations supported by the server.

### DTD
> 
```
<!ELEMENT supported-collation-set (supported-collation*)>

<!ELEMENT supported-collation (#PCDATA)>
```

###Example
> 
>
```xml
<C:supported-collation-set
   xmlns:C="urn:ietf:params:xml:ns:caldav">
 <C:supported-collation>i;ascii-casemap</C:supported-collation>
 <C:supported-collation>i;octet</C:supported-collation>
</C:supported-collation-set>
```
