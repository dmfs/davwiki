<!-- --- title: http://calendarserver.org/ns/:getctag -->

<div id="summary-box" markdown="1">
<h4>Summary</h4>

#####Specification
[[caldav-ctag]]
[Section 4.1](http://svn.calendarserver.org/repository/calendarserver/CalendarServer/trunk/doc/Extensions/caldav-ctag.txt)

#####Type
Property

#####Protected
MUST

#####Returned by allprop
SHOULD

#####Valid for resource types

* [[urn:ietf:params:xml:ns:caldav:calendar]]
* [[urn:ietf:params:xml:ns:caldav:schedule-inbox]]
* [[urn:ietf:params:xml:ns:caldav:schedule-outbox]]
* also commonly used for [[urn:ietf:params:xml:ns:carddav:addressbook]]
</div>

###Purpose
> Specifies a "synchronization" token used to indicate when the contents of a calendar or scheduling Inbox or Outbox collection have changed.

###Conformance
> This property MUST be defined on a calendar or scheduling Inbox or Outbox collection resource.  It MUST be protected and SHOULD be returned by a PROPFIND DAV:allprop request (as defined in Section 12.14.1 of [RFC2518]).

###COPY/MOVE behavior
Not specified in [[caldav-ctag]]. It probably should be similar to [[DAV::getetag]].

###Description
> The CS:getctag property allows clients to quickly determine if the contents of a calendar or scheduling Inbox or Outbox collection have changed since the last time a "synchronization" operation was done. The CS:getctag property value MUST change each time the contents of the calendar or scheduling Inbox or Outbox collection change, and each change MUST result in a value that is different from any other used with that collection URI.

###Example
> add any examples
>
```xml
<T:getctag xmlns:T="http://calendarserver.org/ns/"
>ABCD-GUID-IN-THIS-COLLECTION-20070228T122324010340</T:getctag>
```

### DTD
> Add DTD
```
<!ELEMENT getctag #PCDATA>
```

##Comments
CTags are widely supported by servers and clients, not only for calendar collections, but also for address book collections. However, CTag is not an official standard and has been superseded by [[DAV::sync-token]], which has additional semantics for synchronization.