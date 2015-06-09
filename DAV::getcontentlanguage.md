<!-- --- title: DAV::getcontentlanguage -->

<div id="summary-box" markdown="1">
###Summary

<dl>
<dt>Specification</dt>
<dd markdown="1">[[RFC 4918]]
[Section 15.3](http://tools.ietf.org/html/rfc4918#section-15.3)
</dd>
<dt>Type</dt>
<dd markdown="1">Property
</dd>
<dt>Protected</dt>
<dd markdown="1">SHOULD NOT
</dd>
<dt>Returned by allprop</dt>
<dd markdown="1">MUST
</dd>
<dt>Valid for resource types</dt>
<dd markdown="1">any DAV-compliant resource that returns the [[Content-Language header|headers/Content-Language]] on a [[GET]]
</dd>
</dl>

</div>

<!-- below is a list of common sections for property definitions. Adjust the list as needed. Don't forget to block-quote any text that's copied from the RFC -->

###Purpose
> Contains the Content-Language header value (from [Section 14.12 of RFC 2616](http://tools.ietf.org/html/rfc2616#section-14.12)) as it would be returned by a [[GET]] without accept headers.

###Value
> language-tag (language-tag is defined in [Section 3.10 of RFC 2616](http://tools.ietf.org/html/rfc2616#section-3.10))

###Protected
> SHOULD NOT be protected, so that clients can reset the language. Note that servers implementing [[RFC 2518]] might have made this a protected property as this is a new requirement.

###COPY/MOVE behavior
> This property value SHOULD be preserved in COPY and MOVE operations.

###Description
> The DAV:getcontentlanguage property MUST be defined on any DAV-compliant resource that returns the [[Content-Language header|headers/Content-Language]] on a [[GET]].

### DTD
> 
```
<!ELEMENT getcontentlanguage (#PCDATA) >

```
