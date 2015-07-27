<!-- --- title: urn:ietf:params:xml:ns:carddav:addressbook-home-set -->

<div id="summary-box" markdown="1">
<h4>Summary</h4>

<dl>
<dt>Specification</dt>
<!-- insert the RFC number and the link to the original specification of this property -->
<dd markdown="1">[[RFC 6352]]
<a href="http://tools.ietf.org/html/rfc6352#section-7.1.1">Section 7.1.1</a>
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
