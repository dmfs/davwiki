<!-- --- title: List of DAV properties -->

### [[RFC 4791]] (CalDAV)

| Property | Purpose | Value   |
|----------|---------|-------|
| [[CALDAV:calendar-description|urn:ietf:params:xml:ns:caldav:calendar-description]] | Provides a human-readable description of the calendar collection. | String |
| [[CALDAV:calendar-home-set|urn:ietf:params:xml:ns:caldav:calendar-home-set]] | Identifies the URL of any WebDAV collections that contain calendar collections owned by the associated principal resource. | A list of DAV::href elements. |
| [[CALDAV:calendar-timezone|urn:ietf:params:xml:ns:caldav:calendar-timezone]] | Specifies a time zone on a calendar collection.| An iCalendar object with exactly one VTIMEZONE component. |
| [[CALDAV:max-attendees-per-instance|urn:ietf:params:xml:ns:caldav:max-attendees-per-instance]] | Provides a numeric value indicating the maximum number of ATTENDEE properties in any instance of a calendar object resource stored in a calendar collection. | A numeric value |
| [[CALDAV:max-date-time|urn:ietf:params:xml:ns:caldav:max-date-time]] | Provides a DATE-TIME value indicating the latest date and time (in UTC) that the server is willing to accept for any DATE or DATE-TIME value in a calendar object resource stored in a calendar collection. | An iCalendar format DATE-TIME value in UTC |
| [[CALDAV:max-instances|urn:ietf:params:xml:ns:caldav:max-instances]]| Provides a numeric value indicating the maximum number of recurrence instances that a calendar object resource stored in a calendar collection can generate. | A numeric value |
| [[CALDAV:max-resource-size|urn:ietf:params:xml:ns:caldav:max-resource-size]] | Provides a numeric value indicating the maximum size of a resource in octets that the server is willing to accept when a calendar object resource is stored in a calendar collection. | A numeric value |
| [[CALDAV:min-date-time|urn:ietf:params:xml:ns:caldav:min-date-time]] | Provides a DATE-TIME value indicating the earliest date and time (in UTC) that the server is willing to accept for any DATE or DATE-TIME value in a calendar object resource stored in a calendar collection. | An iCalendar format DATE-TIME value in UTC |
| [[CALDAV:supported-calendar-component-set|urn:ietf:params:xml:ns:caldav:supported-calendar-component-set]] | Specifies the calendar component types (e.g., VEVENT, VTODO, etc.) that calendar object resources can contain in the calendar collection. | 
| [[CALDAV:supported-calendar-data|urn:ietf:params:xml:ns:caldav:supported-calendar-data]] | Specifies what media types are allowed for calendar object resources in a calendar collection. | 
| [[CALDAV:supported-collation-set|urn:ietf:params:xml:ns:caldav:supported-collation-set]] | Identifies the set of collations supported by the server for text matching operations. |

### [[RFC 4918]] (WebDAV)

| Property | Purpose | Value |
|----------|---------|-------|
| [[DAV:creationdate|DAV::creationdate]] | Records the time and date the resource was created. | date-time |
| [[DAV:displayname|DAV::displayname]] | Provides a name for the resource that is suitable for presentation to a user. | text |
| [[DAV:getcontentlanguage|DAV::getcontentlanguage]] | Contains the [[Content-Language header|headers/Content-Language]] value as it would be returned by a [[GET]] without accept headers. | language-tag |
| [[DAV:getcontentlength|DAV::getcontentlength]] | Contains the Content-Length header returned by a [[GET]] without accept. | decimal number |
| [[DAV:getcontenttype|DAV::getcontenttype]] | Contains the Content-Type header value as it would be returned by a [[GET]] without accept headers. | media-type |
| [[DAV:getetag|DAV::getetag]] | Contains the ETag header value as it would be returned by a [[GET]] without accept headers. | entity-tag |
| [[DAV:getlastmodified|DAV::getlastmodified]] | Contains the Last-Modified header value as it would be returned by a [[GET]] method without accept headers. | rfc1123-date |
| [[DAV:lockdiscovery|DAV::lockdiscovery]] | Describes the active locks on a resource | A list of active locks. |
| [[DAV:resourcetype|DAV::resourcetype]] | Specifies the nature of the resource. | 
| [[DAV:supportedlock|DAV::supportedlock]] | To provide a listing of the lock capabilities supported by the resource. | A list of lock entries |


### [[RFC 6352]] (CardDAV)

| Property | Purpose | Value |
|----------|---------|-------|
| [[CARDDAV:addressbook-description|urn:ietf:params:xml:ns:carddav:addressbook-description]] | Provides a human-readable description of the address book collection. | Any text. |
| [[CARDDAV:addressbook-home-set|urn:ietf:params:xml:ns:carddav:addressbook-home-set]] | Identifies the URL of any WebDAV collections that contain address book collections owned by the associated principal resource. | 
| [[CARDDAV:max-resource-size|urn:ietf:params:xml:ns:carddav:max-resource-size]] | Provides a numeric value indicating the maximum size in octets of a resource that the server is willing to accept when an address object resource is stored in an address book collection. | Any text representing a numeric value. |
| [[CARDDAV:principal-address|urn:ietf:params:xml:ns:carddav:principal-address]] | Identifies the URL of an address object resource that corresponds to the user represented by the principal. | 
| [[CARDDAV:supported-address-data|urn:ietf:params:xml:ns:carddav:supported-address-data]] | Specifies what media types are allowed for address object resources in an address book collection. |
| [[CARDDAV:supported-collation-set|urn:ietf:params:xml:ns:carddav:supported-collation-set]] | Identifies the set of collations supported by the server for text matching operations. | 

