<!-- --- title: DAV::displayname -->

<div id="summary-box" markdown="1">
###Summary

#####Specification
[[RFC 4918]]
[Section 15.2](http://tools.ietf.org/html/rfc4918#section-15.2).

#####Type
Property

#####Value
text

#####Protected
SHOULD NOT

#####Returned by allprop
MUST

#####Valid for resource types
all
</div>

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
