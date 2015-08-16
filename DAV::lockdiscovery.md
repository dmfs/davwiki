<!-- --- title: DAV::lockdiscovery -->
<!-- --- link_title: DAV:lockdiscovery -->
<!-- --- current_spec: RFC 4918 -->
<!-- --- current_spec_rfc_number: 4918 -->
<!-- --- current_spec_rfc_section: 15.8 -->
<!-- --- xml_namespace: DAV: -->
<!-- --- xml_element: lockdiscovery -->
<!-- --- type: property -->
<!-- --- purpose: Describes the active locks on a resource. -->
<!-- --- value: a list of [[active locks|DAV::activelock]]. -->
<!-- --- protected: MUST -->
<!-- --- allprop: MUST -->
<!-- x--- valid_for: TODO -->

<!-- >>> property-summary-box --><!-- <<< -->

<!-- below is a list of common sections for property definitions. Adjust the list as needed. Don't forget to block-quote any text that's copied from the RFC -->

###Purpose
> Describes the active locks on a resource.

###Value
A list of [[active locks|DAV::activelock]].

###Protected
> MUST be protected. Clients change the list of locks through [[LOCK]] and [[UNLOCK]], not through [[PROPPATCH]].

###COPY/MOVE behavior
>  The value of this property depends on the lock state of the destination, not on the locks of the source resource. Recall that locks are not moved in a [[MOVE]] operation.

###Description
>  Returns a listing of who has a lock, what type of lock he has, the timeout type and the time remaining on the timeout, and the associated lock token. Owner information MAY be omitted if it is considered sensitive. If there are no locks, but the server supports locks, the property will be present but contain zero '[[activelock|DAV::activelock]]' elements. If there are one or more locks, an '[[activelock|DAV::activelock]]' element appears for each lock on the resource. This property is NOT lockable with respect to write locks ([Section 7](http://tools.ietf.org/html/rfc4918#section-7)).

### DTD
> 
```
<!ELEMENT lockdiscovery (activelock)* >
```

###Examples

####Retrieving DAV:lockdiscovery

**Request**

>
```
PROPFIND /container/ HTTP/1.1
Host: www.example.com
Content-Length: xxxx
Content-Type: application/xml; charset="utf-8"

<?xml version="1.0" encoding="utf-8" ?>
<D:propfind xmlns:D='DAV:'>
  <D:prop><D:lockdiscovery/></D:prop>
</D:propfind>
```

**Response**

>
```
HTTP/1.1 207 Multi-Status
Content-Type: application/xml; charset="utf-8"
Content-Length: xxxx

<?xml version="1.0" encoding="utf-8" ?>
<D:multistatus xmlns:D='DAV:'>
<D:response>
 <D:href>http://www.example.com/container/</D:href>
 <D:propstat>
   <D:prop>
     <D:lockdiscovery>
      <D:activelock>
       <D:locktype><D:write/></D:locktype>
       <D:lockscope><D:exclusive/></D:lockscope>
       <D:depth>0</D:depth>
       <D:owner>Jane Smith</D:owner>
       <D:timeout>Infinite</D:timeout>
       <D:locktoken>
         <D:href
     >urn:uuid:f81de2ad-7f3d-a1b2-4f3c-00a0c91a9d76</D:href>
       </D:locktoken>
       <D:lockroot>
         <D:href>http://www.example.com/container/</D:href>
       </D:lockroot>
      </D:activelock>
     </D:lockdiscovery>
   </D:prop>
   <D:status>HTTP/1.1 200 OK</D:status>
 </D:propstat>
</D:response>
</D:multistatus>
```
>
>This resource has a single exclusive write lock on it, with an
>infinite timeout.





















