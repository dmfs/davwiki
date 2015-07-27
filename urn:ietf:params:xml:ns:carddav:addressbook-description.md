<!-- --- title: urn:ietf:params:xml:ns:carddav:addressbook-description -->

<div id="summary-box" markdown="1">
<h4>Summary</h4>

<dl>
<dt>Specification</dt>
<!-- insert the RFC number and the link to the original specification of this property -->
<dd markdown="1">[[RFC 6352]]
[Section 6.2.1](http://tools.ietf.org/html/rfc6352#section-6.2.1)
</dd>
<dt>Type</dt>
<dd markdown="1">Property
</dd>
<dt>Protected</dt>
<dd markdown="1">SHOULD NOT
</dd>
<dt>Returned by allprop</dt>
<dd markdown="1">SHOULD NOT
</dd>
<dt>Valid for resource types</dt>
<dd markdown="1">[[urn:ietf:params:xml:ns:carddav:addressbook]]
</dd>
</dl>

</div>

<!-- below is a list of common sections for property definitions. Adjust the list as needed. Don't forget to block-quote any text that's copied from the RFC -->

###Purpose
> Provides a human-readable description of the address book collection.

###Value
> Any text.

###Protected
> SHOULD NOT be protected so that users can specify a description.

###COPY/MOVE behavior
> This property value SHOULD be preserved in [[COPY]] and [[MOVE]] operations.

###Allprop behavior
> SHOULD NOT be returned by a [[PROPFIND]] [[DAV:allprop]] request.

###Description
> This property contains a description of the address book collection that is suitable for presentation to a user. The [[xml:lang]] attribute can be used to add a language tag for the value of this property.

### DTD
> 
```
<!ELEMENT addressbook-description (#PCDATA)>
<!-- PCDATA value: string -->
```

###Example
> 
>
```xml
<C:addressbook-description xml:lang="fr-CA"
  xmlns:C="urn:ietf:params:xml:ns:carddav"
>Adresses de Oliver Daboo</C:addressbook-description>
```
