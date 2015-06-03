<!-- --- title: DAV::getcontentlength -->

<div id="summary-box" markdown="1">
###Summary

#####Specification
[[RFC 4918]]
[Section 15.4](http://tools.ietf.org/html/rfc4918#section-15.4).

#####Type
Property

#####Value
Number

#####Protected
MUST

#####Returned by allprop
MUST

#####Valid for resource types
any DAV-compliant resource that returns the Content-Length header in response to a GET
</div>

###Purpose
> Contains the Content-Length header returned by a GET without accept headers.

###Value
> See [Section 14.13 of RFC 2616](http://tools.ietf.org/html/rfc2616#section-14.13)

###Protected
> This property is computed, therefore protected.

###COPY/MOVE behavior
> This property value is dependent on the size of the destination resource, not the value of the property on the source resource.

###Description
> The DAV:getcontentlength property MUST be defined on any DAV-compliant resource that returns the Content-Length header in response to a GET.

### DTD
> 
```
<!ELEMENT getcontentlength (#PCDATA) >

```
