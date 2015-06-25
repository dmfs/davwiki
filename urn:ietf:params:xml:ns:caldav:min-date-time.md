<!-- --- title: urn:ietf:params:xml:ns:caldav:min-date-time -->

<div id="summary-box" markdown="1">

###Summary

<dl>
<dt>Specification</dt>
<!-- insert the RFC number and the link to the original specification of this property -->
<dd markdown="1">[[RFC 4791]] [Section 5.2.6](http://tools.ietf.org/html/rfc4791#section-5.2.6)
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
> Provides a DATE-TIME value indicating the earliest date and time (in UTC) that the server is willing to accept for any DATE or DATE-TIME value in a calendar object resource stored in a calendar collection.

###Value
An iCalendar format DATE-TIME value in UTC

###Conformance
> This property MAY be defined on any [[calendar collection|urn:ietf:params:xml:ns:caldav:calendar]]. If defined, it MUST be protected and SHOULD NOT be returned by a [[PROPFIND]] [[DAV::allprop]] request (as defined in [Section 12.14.1 of RFC 2518](https://tools.ietf.org/html/rfc2518#section-12.14.1)).

###Description
> The CALDAV:min-date-time is used to specify an iCalendar DATE-TIME value in UTC that indicates the earliest inclusive date that the server is willing to accept for any explicit DATE or DATE-TIME value in a calendar object resource stored in a calendar collection. Any attempt to store a calendar object resource using a DATE or DATE-TIME value earlier than this value MUST result in an error, with the CALDAV:min-date-time precondition ([Section 5.3.2.1](https://tools.ietf.org/html/rfc4791#section-5.3.2.1)) being violated. Note that servers MUST accept recurring components that specify instances beyond this limit, provided none of those instances have been overridden. In that case, the server MAY simply ignore those instances outside of the acceptable range when processing reports on the calendar object resource.  In the absence of this property, the client can assume any valid iCalendar date may be used at least up to the CALDAV:max-date-time value, if that is defined.

### DTD
> 
```
<!ELEMENT min-date-time (#PCDATA)>
PCDATA value: an iCalendar format DATE-TIME value in UTC
```

###Example
> 
>
```xml
<C:min-date-time xmlns:C="urn:ietf:params:xml:ns:caldav"
>19000101T000000Z</C:min-date-time>
```
