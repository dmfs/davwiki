<!-- --- title: DAV::getcontentlength -->

<div id="summary-box" markdown="1">
###Summary

<dl>
<dt>Specification</dt>
<dd markdown="1">[[RFC 4918]]
[Section 15.4](http://tools.ietf.org/html/rfc4918#section-15.4)
</dd>
<dt>Type</dt>
<dd markdown="1">Property
</dd>
<dt>Protected</dt>
<dd markdown="1">MUST
</dd>
<dt>Returned by allprop</dt>
<dd markdown="1">MUST
</dd>
<dt>Valid for resource types</dt>
<dd markdown="1">any DAV-compliant resource that returns the [[Content-Length header|headers/Content-Lenght]] in response to a [[GET]]
</dd>
</dl>

</div>

<!-- below is a list of common sections for property definitions. Adjust the list as needed. Don't forget to block-quote any text that's copied from the RFC -->

###Purpose
> Contains the Content-Length header returned by a GET without accept headers.

###Value
> See [Section 14.13 of RFC 2616](http://tools.ietf.org/html/rfc2616#section-14.13)

###Protected
> This property is computed, therefore protected.

###COPY/MOVE behavior
> This property value is dependent on the size of the destination resource, not the value of the property on the source resource.

###Description
> The DAV:getcontentlength property MUST be defined on any DAV-compliant resource that returns the [[Content-Length header|headers/Content-Lenght]] in response to a [[GET]].

### DTD
> 
```
<!ELEMENT getcontentlength (#PCDATA) >

```
