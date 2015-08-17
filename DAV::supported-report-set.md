<!-- --- title: DAV::supported-report-set -->
<!-- --- link_title: DAV:supported-report-set -->
<!-- --- current_spec: RFC 3253 -->
<!-- --- current_spec_rfc_number: 3253 -->
<!-- --- current_spec_rfc_section: 3.1.5 -->
<!-- --- xml_namespace: DAV: -->
<!-- --- xml_element: supported-report-set -->
<!-- --- type: property -->
<!-- --- purpose: identifies the reports that are supported by the resource -->
<!-- --- value: a list of [[DAV:supported-report|DAV::supported-report]] elements -->
<!-- --- protected: MUST -->
<!-- --- allprop: SHOULD NOT -->
<!-- --- valid_for: every resource that supports the [[REPORT]] method -->

<!-- >>> property-summary-box --><!-- <<< -->

###Purpose
> This property identifies the reports that are supported by the resource.

###Protected
This property is protected.

###COPY/MOVE behavior
Not specfied by [[RFC 3253]]

### Example
TODO

### DTD
>
```
<!ELEMENT supported-report-set (supported-report*)>
```

The only expected child element is [[DAV:supported-report|DAV::supported-report]].

