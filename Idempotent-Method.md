<!-- --- title: Idempotent Method -->
<!-- --- method_property_description: idempotent -->

###Description

From [RFC 7231, Section 4.2.2](https://tools.ietf.org/html/rfc7231#section-4.2.2):

>A request method is considered "idempotent" if the intended effect on
>the server of multiple identical requests with that method is the
>same as the effect for a single such request.  Of the request methods
>defined by this specification, [[PUT]], [[DELETE]], and [[safe request methods|Safe Method]]
>are idempotent.
>
>Like the definition of safe, the idempotent property only applies to
>what has been requested by the user; a server is free to log each
>request separately, retain a revision control history, or implement
>other non-idempotent side effects for each idempotent request.
>
>Idempotent methods are distinguished because the request can be
>repeated automatically if a communication failure occurs before the
>client is able to read the server's response.  For example, if a
>client sends a [[PUT]] request and the underlying connection is closed
>before any response is received, then the client can establish a new
>connection and retry the idempotent request.  It knows that repeating
>the request will have the same intended effect, even if the original
>request succeeded, though the response might differ.

<!-- >>> methods-for-property --><!-- <<< -->

