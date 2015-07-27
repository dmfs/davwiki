<!-- --- title: urn:ietf:params:xml:ns:carddav:supported-collation-set -->

<div id="summary-box" markdown="1">
<h4>Summary</h4>

<dl>
<dt>Specification</dt>
<!-- insert the RFC number and the link to the original specification of this property -->
<dd markdown="1">[[RFC 6352]]
<a href="http://tools.ietf.org/html/rfc6352#section-8.3.1">Section 8.3.1</a>
</dd>
<dt>Type</dt>
<dd markdown="1">Property
</dd>
<dt>Protected</dt>
<dd markdown="1">MUST
</dd>
<dt>Returned by allprop</dt>
<dd markdown="1">SHOULD NOT
</dd>
<dt>Valid for resource types</dt>
<dd markdown="1">This property MUST be defined on any resource that supports a report that does text matching.
</dd>
</dl>

</div>

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
