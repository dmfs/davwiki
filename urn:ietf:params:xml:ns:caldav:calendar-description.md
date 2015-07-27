<!-- --- title: urn:ietf:params:xml:ns:caldav:calendar-description -->

<div id="summary-box" markdown="1">
<h4>Summary</h4>

<dl>
<dt>Specification</dt>
<!-- insert the RFC number and the link to the original specification of this property -->
<dd markdown="1">[[RFC 4791]]
[Section 5.2.1](http://tools.ietf.org/html/rfc4791#section-5.2.1)
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
<dd markdown="1">[[urn:ietf:params:xml:ns:caldav:calendar]]
</dd>
</dl>

</div>

<!-- below is a list of common sections for property definitions. Adjust the list as needed. Don't forget to block-quote any text that's copied from the RFC -->

###Purpose
> Provides a human-readable description of the calendar collection.

###Value
String

###Conformance
> This property MAY be defined on any [[calendar collection|urn:ietf:params:xml:ns:caldav:calendar]]. If defined, it MAY be protected and SHOULD NOT be returned by a [[PROPFIND]] [[DAV::allprop]] request (as defined in [Section 12.14.1 of RFC 2518](https://tools.ietf.org/html/rfc2518#section-12.14.1)). An [[xml:lang]] attribute indicating the human language of the description SHOULD be set for this property by clients or through server provisioning.  Servers MUST return any [[xml:lang]] attribute if set for the property.

###Description
>  If present, the property contains a description of the calendar collection that is suitable for presentation to a user. If not present, the client should assume no description for the calendar collection.

### DTD
> 
```
<!ELEMENT calendar-description (#PCDATA)>
PCDATA value: string
```

###Example
> 
>
```xml
<C:calendar-description xml:lang="fr-CA"
    xmlns:C="urn:ietf:params:xml:ns:caldav"
>Calendrier de Mathilde Desruisseaux</C:calendar-description>
```
