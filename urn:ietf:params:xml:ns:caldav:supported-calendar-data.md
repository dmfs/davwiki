<!-- --- title: urn:ietf:params:xml:ns:caldav:supported-calendar-data -->

<div id="summary-box" markdown="1">
<h4>Summary</h4>

<dl>
<dt>Specification</dt>
<!-- insert the RFC number and the link to the original specification of this property -->
<dd markdown="1">[[RFC 4791]]
<a href="http://tools.ietf.org/html/rfc4791#section-5.2.4">Section 5.2.4</a>
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
> Specifies what media types are allowed for calendar object resources in a calendar collection.

###Conformance
> This property MAY be defined on any [[calendar collection|urn:ietf:params:xml:ns:caldav:calendar]]. If defined, it MUST be protected and SHOULD NOT be returned by a [[PROPFIND]] [[DAV::allprop]] request (as defined in [Section 12.14.1 of RFC 2518](https://tools.ietf.org/html/rfc2518#section-12.14.1)).

###Description
> The CALDAV:supported-calendar-data property is used to  specify the media type supported for the calendar object resources  contained in a given calendar collection (e.g., iCalendar version 2.0). Any attempt by the client to store calendar object resources with a media type not listed in this property MUST result in an error, with the CALDAV:supported-calendar-data precondition ([Section 5.3.2.1](https://tools.ietf.org/html/rfc4791#section-5.3.2.1)) being violated. In the absence of this property, the server MUST only accept data with the media type "text/calendar" and iCalendar version 2.0, and clients can assume that the server will only accept this data.

### DTD
> 
```
<!ELEMENT supported-calendar-data (calendar-data+)>
```

###Example
> 
>
```xml
<C:supported-calendar-data
    xmlns:C="urn:ietf:params:xml:ns:caldav">
    <C:calendar-data content-type="text/calendar" version="2.0"/>
</C:supported-calendar-data>
```
