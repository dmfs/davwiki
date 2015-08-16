<!-- --- title: DAV::displayname -->
<!-- --- link_title: DAV:displayname -->
<!-- --- current_spec: RFC 4918 -->
<!-- --- current_spec_rfc_number: 4918 -->
<!-- --- current_spec_rfc_section: 15.2 -->
<!-- --- xml_namespace: DAV: -->
<!-- --- xml_element: displayname -->
<!-- --- type: property -->
<!-- --- purpose: Provides a name for the resource that is suitable for presentation to a user. -->
<!-- --- value: any text-->
<!-- --- protected: SHOULD NOT -->
<!-- --- allprop: MUST -->
<!-- --- valid_for: all DAV compliant resources -->

<!-- >>> property-summary-box --><!-- <<< -->

<!-- below is a list of common sections for property definitions. Adjust the list as needed. Don't forget to block-quote any text that's copied from the RFC -->

###Purpose
> Provides a name for the resource that is suitable for presentation to a user.

###Value
> Any text.

###Protected
> SHOULD NOT be protected.  Note that servers implementing [[RFC 2518]] might have made this a protected property as this is a new requirement.

###COPY/MOVE behavior
> This property value SHOULD be preserved in COPY and MOVE operations.

###Description
> Contains a description of the resource that is suitable for presentation to a user. This property is defined on the resource, and hence SHOULD have the same value independent of the Request-URI used to retrieve it (thus, computing this property based on the Request-URI is deprecated). While generic clients might display the property value to end users, client UI designers must understand that the method for identifying resources is still the URL. Changes to DAV:displayname do not issue moves or copies to the server, but simply change a piece of meta-data on the individual resource. Two resources can have the same DAV:displayname value even within the same collection.

### DTD
>
```
<!ELEMENT displayname (#PCDATA) >
```
