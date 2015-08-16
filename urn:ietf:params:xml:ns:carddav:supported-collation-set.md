<!-- --- title: urn:ietf:params:xml:ns:carddav:supported-collation-set -->
<!-- --- link_title: CARDDAV:supported-collation-set -->
<!-- --- current_spec: RFC 6352 -->
<!-- --- current_spec_rfc_number: 6352 -->
<!-- --- current_spec_rfc_section: 8.3.1 -->
<!-- --- xml_namespace: urn:ietf:params:xml:ns:carddav -->
<!-- --- xml_element: supported-collation-set -->
<!-- --- type: property -->
<!-- --- purpose: Identifies the set of collations supported by the server for text matching operations. -->
<!-- --- value: a list of [[CARDDAV::supported-collation|urn:ietf:params:xml:ns:carddav:supported-collation]] elements -->
<!-- --- protected: MUST -->
<!-- --- allprop: SHOULD NOT -->
<!-- --- valid_for: This property MUST be defined on any resource that supports a report that does text matching. -->

<!-- >>> property-summary-box --><!-- <<< -->

<!-- below is a list of common sections for property definitions. Adjust the list as needed. Don't forget to block-quote any text that's copied from the RFC -->

###Purpose
> Identifies the set of collations supported by the server for text matching operations.

###Protected
> MUST be protected as it indicates support provided by the server.

###COPY/MOVE behavior
> This property value MUST be preserved in [[COPY]] and [[MOVE]] operations.

###Allprop behavior
> SHOULD NOT be returned by a [[PROPFIND]] [[DAV:allprop]] request.

###Description
> The CARDDAV:supported-collation-set property contains two or more [[CARDDAV:supported-collation|urn:ietf:params:xml:ns:carddav:supported-collation]] elements that specify the identifiers of the collations supported by the server.

### DTD
> 
```
<!ELEMENT supported-collation-set (
      supported-collation
      supported-collation
      supported-collation*)>
<!-- Both "i;ascii-casemap" and "i;unicode-casemap"
     will be present -->

<!ELEMENT supported-collation (#PCDATA)>
```

###Example
> 
>
```xml
<C:supported-collation-set
  xmlns:C="urn:ietf:params:xml:ns:carddav">
  <C:supported-collation>i;ascii-casemap</C:supported-collation>
  <C:supported-collation>i;octet</C:supported-collation>
  <C:supported-collation>i;unicode-casemap</C:supported-collation>
</C:supported-collation-set>
```
