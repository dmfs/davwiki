<!-- --- title: DAV::supportedlock -->
<!-- --- link_title: DAV:supportedlock-->
<!-- --- current_spec: RFC 4918 -->
<!-- --- current_spec_rfc_number: 4918 -->
<!-- --- current_spec_rfc_section: 15.10 -->
<!-- --- xml_namespace: DAV: -->
<!-- --- xml_element: supportedlock -->
<!-- --- type: property -->
<!-- --- purpose: To provide a listing of the lock capabilities supported by the resource. -->
<!-- --- value: a list of [[lock entries|DAV::lockentry]] -->
<!-- --- protected: MUST -->
<!-- --- allprop: MUST -->
<!-- x--- valid_for:  --> <!-- TODO -->

<!-- >>> property-summary-box --><!-- <<< -->

<!-- below is a list of common sections for property definitions. Adjust the list as needed. Don't forget to block-quote any text that's copied from the RFC -->

###Purpose
> To provide a listing of the lock capabilities supported by the resource.

###Value
A list of [[lock entries|DAV::lockentry]]

###Protected
> MUST be protected. Servers, not clients, determine what lock mechanisms are supported.

###COPY/MOVE behavior
> This property value is dependent on the kind of locks supported at the destination, not on the value of the property at the source resource.  Servers attempting to COPY to a destination should not attempt to set this property at the destination.

###Description
> Returns a listing of the combinations of scope and access types that may be specified in a lock request on the resource. Note that the actual contents are themselves controlled by access controls, so a server is not required to provide information the client is not authorized to see. This property is  NOT lockable with respect to write locks ([Section 7](http://tools.ietf.org/html/rfc4918#section-7).)

### DTD
> 
```
<!ELEMENT supportedlock (lockentry)* >
```

###Examples

####Retrieving Named Properties

**Request**

>
```
PROPFIND /container/ HTTP/1.1
Host: www.example.com
Content-Length: xxxx
Content-Type: application/xml; charset="utf-8"

<?xml version="1.0" encoding="utf-8" ?>
<D:propfind xmlns:D="DAV:">
  <D:prop><D:supportedlock/></D:prop>
</D:propfind>
```

**Response**

>
```
HTTP/1.1 207 Multi-Status
Content-Type: application/xml; charset="utf-8"
Content-Length: xxxx

<?xml version="1.0" encoding="utf-8" ?>
<D:multistatus xmlns:D="DAV:">
<D:response>
 <D:href>http://www.example.com/container/</D:href>
 <D:propstat>
   <D:prop>
     <D:supportedlock>
       <D:lockentry>
         <D:lockscope><D:exclusive/></D:lockscope>
         <D:locktype><D:write/></D:locktype>
       </D:lockentry>
       <D:lockentry>
         <D:lockscope><D:shared/></D:lockscope>
         <D:locktype><D:write/></D:locktype>
       </D:lockentry>
     </D:supportedlock>
   </D:prop>
   <D:status>HTTP/1.1 200 OK</D:status>
 </D:propstat>
</D:response>
</D:multistatus>
```

























