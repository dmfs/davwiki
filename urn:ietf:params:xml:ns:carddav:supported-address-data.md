<!-- --- title: urn:ietf:params:xml:ns:carddav:supported-address-data -->

<div id="summary-box" markdown="1">
<h4>Summary</h4>

<dl>
<dt>Specification</dt>
<!-- insert the RFC number and the link to the original specification of this property -->
<dd markdown="1">[[RFC 6352]]
[Section 6.2.2](http://tools.ietf.org/html/rfc6352#section-6.2.2)
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
<dd markdown="1">[[urn:ietf:params:xml:ns:carddav:addressbook]]
</dd>
</dl>

</div>

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
