<!-- --- title: urn:ietf:params:xml:ns:caldav:calendar -->

<div id="summary-box" markdown="1">
<h4>Summary</h4>

#####Specification
[[RFC 4791]]
[Section 4.2](http://tools.ietf.org/html/rfc4791#section-4.2).

#####Type
Resource type
</div>


  A calendar collection contains calendar object resources that
   represent calendar components within a calendar.  A calendar
   collection is manifested to clients as a WebDAV resource collection
   identified by a URL.  A calendar collection MUST report the DAV:
   collection and CALDAV:calendar XML elements in the value of the DAV:
   resourcetype property.  The element type declaration for CALDAV:
   calendar is:

   A calendar collection can be created through provisioning (i.e.,
   automatically created when a user's account is provisioned), or it
   can be created with the MKCALENDAR method (see Section 5.3.1).  This
   method can be useful for a user to create additional calendars (e.g.,
   soccer schedule) or for users to share a calendar (e.g., team events
   or conference rooms).  However, note that this document doesn't
   define the purpose of extra calendar collections.  Users must rely on
   non-standard cues to find out what a calendar collection is for, or
   use the CALDAV:calendar-description property defined in Section 5.2.1
   to provide such a cue.

   The following restrictions are applied to the resources within a
   calendar collection:

>a.  Calendar collections MUST only contain calendar object resources and collections that are not calendar collections, i.e., the only "top-level" non-collection resources allowed in a calendar collection are calendar object resources.  This ensures that calendar clients do not have to deal with non-calendar data in a calendar collection, though they do have to distinguish between calendar object resources and collections when using standard WebDAV techniques to examine the contents of a collection.

>b.  Collections contained in calendar collections MUST NOT contain calendar collections at any depth, i.e., "nesting" of calendar collections within other calendar collections at any depth is not allowed.  This specification does not define how collections contained in a calendar collection are used or how they relate to any calendar object resources contained in the calendar collection.

   Multiple calendar collections MAY be children of the same collection.

###DTD
>
```
<!ELEMENT calendar EMPTY>
```
