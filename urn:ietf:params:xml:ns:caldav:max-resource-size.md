<!-- --- title: urn:ietf:params:xml:ns:caldav:max-resource-size -->

<div id="summary-box" markdown="1">
<h4>Summary</h4>

<dl>
<dt>Specification</dt>
<!-- insert the RFC number and the link to the original specification of this property -->
<dd markdown="1">[[RFC 4791]]
[Section 5.2.5](http://tools.ietf.org/html/rfc4791#section-5.2.5)
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
<dd markdown="1">[[urn:ietf:params:xml:ns:caldav:calendar]]
</dd>
</dl>

</div>

<!-- below is a list of common sections for property definitions. Adjust the list as needed. Don't forget to block-quote any text that's copied from the RFC -->

###Purpose
> Provides a numeric value indicating the maximum size of a resource in octets that the server is willing to accept when a calendar object resource is stored in a calendar collection.

###Value
A numeric value (positive integer)

###Conformance
> This property MAY be defined on any [[calendar collection|urn:ietf:params:xml:ns:caldav:calendar]]. If defined, it MUST be protected and SHOULD NOT be returned by a [[PROPFIND]] [[DAV::allprop]] request (as defined in [Section 12.14.1 of RFC 2518](https://tools.ietf.org/html/rfc2518#section-12.14.1)).

###Description
>  The CALDAV:max-resource-size is used to specify a numeric value that represents the maximum size in octets that the server is willing to accept when a calendar object resource is stored in a calendar collection. Any attempt to store a calendar object resource exceeding this size MUST result in an error, with the CALDAV:max-resource-size precondition ([Section 5.3.2.1](https://tools.ietf.org/html/rfc4791#section-5.3.2.1)) being violated. In the absence of this property, the client can assume that the server will allow storing a resource of any reasonable size.

### DTD
> 
```
<!ELEMENT max-resource-size (#PCDATA)>
PCDATA value: a numeric value (positive integer)
```

###Example
> 
>
```xml
<C:max-resource-size xmlns:C="urn:ietf:params:xml:ns:caldav"
>102400</C:max-resource-size>
```
