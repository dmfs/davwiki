<!-- --- title: DAV::creationdate -->

<div id="summary-box" markdown="1">
###Summary

#####Specification
[[RFC 4918]]
[Section 15.1](http://tools.ietf.org/html/rfc4918#section-15.1).

#####Type
Property

#####Value
date-time

#####Protected
MAY

#####Returned by allprop
MUST

#####Valid for resource types
all
</div>

###Purpose
> Records the time and date the resource was created.

###Value
> date-time (defined in [[RFC 3339]], see the ABNF in [Section 5.6](http://tools.ietf.org/html/rfc3339#section-5.6).)

###Protected
> MAY be protected.  Some servers allow DAV:creationdate to be changed to reflect the time the document was created if that is more meaningful to the user (rather than the time it was uploaded). Thus, clients SHOULD NOT use this property in synchronization logic (use DAV:getetag instead).

###COPY/MOVE behavior
> This property value SHOULD be kept during a MOVE operation, but is normally re-initialized when a resource is created with a COPY. It should not be set in a COPY.

###Description
> The DAV:creationdate property SHOULD be defined on all DAV compliant resources.  If present, it contains a timestamp of the moment when the resource was created. Servers that are incapable of persistently recording the creation date SHOULD instead leave it undefined (i.e. report "Not Found").


### DTD
> 
```
<!ELEMENT creationdate (#PCDATA) >
```
