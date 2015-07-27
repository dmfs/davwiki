<!-- --- title: urn:ietf:params:xml:ns:carddav:principal-address -->

<div id="summary-box" markdown="1">
<h4>Summary</h4>

<dl>
<dt>Specification</dt>
<!-- insert the RFC number and the link to the original specification of this property -->
<dd markdown="1">[[RFC 6352]]
<a href="http://tools.ietf.org/html/rfc6352#section-7.1.2">Section 7.1.2</a>
</dd>
<dt>Type</dt>
<dd markdown="1">Property
</dd>
<dt>Protected</dt>
<dd markdown="1">MAY
</dd>
<dt>Returned by allprop</dt>
<dd markdown="1">SHOULD NOT
</dd>
<dt>Valid for resource types</dt>
<dd markdown="1">[[DAV::principal]]
</dd>
</dl>

</div>

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
