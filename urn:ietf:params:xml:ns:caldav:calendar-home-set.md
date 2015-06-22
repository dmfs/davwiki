<!-- --- title: urn:ietf:params:xml:ns:caldav:calendar-home-set -->

<div id="summary-box" markdown="1">
###Summary

<dl>
<dt>Specification</dt>
<!-- insert the RFC number and the link to the original specification of this property -->
<dd markdown="1">[[RFC 4791]]
[Section 6.2.1](http://tools.ietf.org/html/rfc4791#section-6.2.1)
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
> Identifies the URL of any WebDAV collections that contain calendar collections owned by the associated principal resource.

### Value
A list of [[DAV::href]] elements.

###Conformance
> This property SHOULD be defined on a principal resource. If defined, it MAY be protected and SHOULD NOT be returned by a [[PROPFIND]] [[DAV:allprop]] request (as defined in [Section 12.14.1 of RFC 2518](https://tools.ietf.org/html/rfc2518#section-12.14.1)).

###Description
> The CALDAV:calendar-home-set property is meant to allow users to easily find the calendar collections owned by the principal.  Typically, users will group all the calendar collections that they own under a common collection. This property specifies the URL of collections that are either calendar collections or ordinary collections that have child or descendant calendar collections owned by the principal.

### DTD
> 
```
<!ELEMENT calendar-home-set (DAV:href*)>
```

###Example
> 
>
```xml
<C:calendar-home-set xmlns:D="DAV:"
                    xmlns:C="urn:ietf:params:xml:ns:caldav">
 <D:href>http://cal.example.com/home/bernard/calendars/</D:href>
</C:calendar-home-set>
```
