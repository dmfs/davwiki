<!-- --- title: Safe Method -->
<!-- --- method_property_description: safe -->

###Description

From [RFC 7231, Section 4.2.1](https://tools.ietf.org/html/rfc7231#section-4.2.1):

> Request methods are considered "safe" if their defined semantics are
> essentially read-only; i.e., the client does not request, and does
> not expect, any state change on the origin server as a result of
> applying a safe method to a target resource.  Likewise, reasonable
> use of a safe method is not expected to cause any harm, loss of
> property, or unusual burden on the origin server.
>
> This definition of safe methods does not prevent an implementation
> from including behavior that is potentially harmful, that is not
> entirely read-only, or that causes side effects while invoking a safe
> method.  What is important, however, is that the client did not
> request that additional behavior and cannot be held accountable for
> it.  For example, most servers append request information to access
> log files at the completion of every response, regardless of the
> method, and that is considered safe even though the log storage might
> become full and crash the server.  Likewise, a safe request initiated
> by selecting an advertisement on the Web will often have the side
> effect of charging an advertising account.
>
> Of the request methods defined by this specification, the [[GET]], [[HEAD]],
> [[OPTIONS]], and [[TRACE]] methods are defined to be safe.

> The purpose of distinguishing between safe and unsafe methods is to
> allow automated retrieval processes (spiders) and cache performance
> optimization (pre-fetching) to work without fear of causing harm.  In
> addition, it allows a user agent to apply appropriate constraints on
> the automated use of unsafe methods when processing potentially
> untrusted content.

> A user agent SHOULD distinguish between safe and unsafe methods when
> presenting potential actions to a user, such that the user can be
> made aware of an unsafe action before it is requested.

> When a resource is constructed such that parameters within the
> effective request URI have the effect of selecting an action, it is
> the resource owner's responsibility to ensure that the action is
> consistent with the request method semantics.  For example, it is
> common for Web-based content editing software to use actions within
> query parameters, such as "page?do=delete".  If the purpose of such a
> resource is to perform an unsafe action, then the resource owner MUST
> disable or disallow that action when it is accessed using a safe
> request method.  Failure to do so will result in unfortunate side
> effects when automated processes perform a [[GET]] on every URI reference
> for the sake of link maintenance, pre-fetching, building a search
> index, etc.

<!-- >>> methods-for-property --><!-- <<< -->

