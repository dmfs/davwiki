<!-- --- title: URL encoding -->
<!-- --- current_spec: RFC 3986 -->
<!-- --- current_spec_rfc_number: 3986 -->

### Bugs

- ownCloud Contacts doubly-encodes/quotes hrefs in addressbook-multiget
  responses (`%2540` represents `@`), but PROPFIND responses quote `@`s only
  once (`%40`). Most requests accept both `@` and `%40`.
  https://github.com/owncloud/contacts/issues/581

- URLs sent to Radicale are unquoted in the response body.
  https://github.com/Kozea/Radicale/issues/298

### Workarounds

- For normalization, decode the URL until it doesn't change anymore. Then
  encode once.

  - Also stop if a remaining `%`-sequence would decode to a reserved character.

### Further references

- http://lists.calconnect.org/pipermail/caldeveloper-l/2015-July/000893.html
