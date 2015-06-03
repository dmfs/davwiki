<!-- --- title: DAV::getcontentlanguage -->

<div id="summary-box" markdown="1">
###Summary

#####Specification
[[RFC 4918]]
[Section 15.3](http://tools.ietf.org/html/rfc4918#section-15.3).

#####Type
Property

#####Value
language-tag

#####Protected
SHOULD NOT

#####Returned by allprop
MUST

#####Valid for resource types
any DAV-compliant resource that returns the Content-Length header in response to a GET
</div>

###Purpose
> Contains the Content-Language header value (from [Section 14.12 of RFC 2616](http://tools.ietf.org/html/rfc2616#section-14.12)) as it would be returned by a GET without accept headers.

###Value
> language-tag (language-tag is defined in [Section 3.10 of RFC 2616](http://tools.ietf.org/html/rfc2616#section-3.10))

###Protected
> SHOULD NOT be protected, so that clients can reset the language. Note that servers implementing [[RFC 2518]] might have made this a protected property as this is a new requirement.

###COPY/MOVE behavior
> This property value is dependent on the size of the destination resource, not the value of the property on the source resource.

###Description
> The DAV:getcontentlength property MUST be defined on any DAV-compliant resource that returns the Content-Length header in response to a GET.

### DTD
> 
```
<!ELEMENT getcontentlanguage (#PCDATA) >

```
