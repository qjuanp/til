A mechanism provided in an HTTP transaction to allow an HTTP user agent (web browser) to provided user name and password per request.

It requires the following HTTP header:

`Authorization: Basic <credentials>`

`credentials` contains in Base64 encoding the user name or user id and password joined bt a signle colon `:`

Specified in:
- RFC 7817 from 2015
- RFC 2617 from 1999 (obsolete document)

---
- [Basic access authentication wikipedia](https://en.wikipedia.org/wiki/Basic_access_authentication)