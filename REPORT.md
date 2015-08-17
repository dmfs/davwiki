<!-- --- title: REPORT Method -->
<!-- --- link_title: REPORT -->
<!-- --- method: REPORT -->
<!-- --- type: method -->
<!-- --- method_properties: safe, idempotent, cacheable -->
<!-- --- valid_success_response_status: 207 Multistatus-->
<!-- --- current_spec: RFC 3253 -->
<!-- --- current_spec_rfc_number: 3253 -->
<!-- --- current_spec_rfc_section: 3.6 -->
<!-- --- purpose: provides an extensible mechanism for obtaining information about a resource -->

[[_TOC_]]

<!-- >>> property-summary-box --><!-- <<< -->

### Description
> A REPORT request is an extensible mechanism for obtaining information
> about a resource.  Unlike a resource property, which has a single
> value, the value of a report can depend on additional information
> specified in the REPORT request body and in the REPORT request
> headers.

### Marshalling

> The body of a REPORT request specifies which report is being
> requested, as well as any additional information that will be used
> to customize the report.
>
> The request MAY include a [[Depth header|headers/depth]]. If no [[Depth header|headers/depth]] is
> included, Depth:0 is assumed.
>
> The response body for a successful request MUST contain the
> requested report.
>
> If a Depth request header is included, the response MUST be a [[207 Multi-Status|207 Multistatus]]. The request MUST be applied separately to the
> collection itself and to all members of the collection that
> satisfy the Depth value. The [[DAV:prop|DAV::prop]] element of a [[DAV:response|DAV::response]]
> for a given resource MUST contain the requested report for that
> resource.

### Preconditions

> ([[DAV:supported-report|DAV::supported-report]]): The specified report MUST be supported by
> the resource identified by the request-URL.

The property [[DAV:supported-report-set|DAV::supported-report-set]] returns all REPORT types supported by the request-URL.

### Postconditions

> ([[DAV:no-modification|DAV::no-modification]]): The REPORT method MUST NOT have changed the
> content or [[dead properties|dead property]] of any resource.

