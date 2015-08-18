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

- It is strongly recommended to avoid unsafe characters in names when `PUT`-ing
  new items or when creating collections. Safe characters include alphanumeric
  characters and `_.-`.

- For normalization, one may decode the URL until:

  - It doesn't change anymore.
  - A remaining `%`-sequence would decode to a reserved character.

  then encode it once. Note that this might change the meaning of the URL and
  accidentally give you a reference to a different item or collection, but
  given the current implementations and their buggyness, this is rather
  unlikely.

### Further references

- http://lists.calconnect.org/pipermail/caldeveloper-l/2015-July/000893.html
