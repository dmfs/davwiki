<!-- --- title: urn:ietf:params:xml:ns:supported-collation-set -->

<div id="summary-box" markdown="1">
<h4>Summary</h4>

<dl>
<dt>Specification</dt>
<!-- insert the RFC number and the link to the original specification of this property -->
<dd markdown="1">[[RFC 4791]]
[Section 7.5.1](http://tools.ietf.org/html/rfc4791#section-7.5.1)
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
