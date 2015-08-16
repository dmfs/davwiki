<!-- --- title: DAV::creationdate -->
<!-- --- link_title: DAV:creationdate -->
<!-- --- current_spec: RFC 4918 -->
<!-- --- current_spec_rfc_number: 4918 -->
<!-- --- current_spec_rfc_section: 15.1 -->
<!-- --- xml_namespace: DAV: -->
<!-- --- xml_element: creationdate -->
<!-- --- type: property -->
<!-- --- purpose: Records the time and date the resource was created. -->
<!-- --- value: date-time -->
<!-- --- protected: MAY -->
<!-- --- allprop: MUST -->
<!-- --- valid_for: all DAV compliant resources -->

<!-- >>> property-summary-box --><!-- <<< -->

<!-- below is a list of common sections for property definitions. Adjust the list as needed. Don't forget to block-quote any text that's copied from the RFC -->

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
