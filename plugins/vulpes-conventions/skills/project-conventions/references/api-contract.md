# API contract

1. For browsers and outside clients, use HTTP with JSON and an OpenAPI 3 document.\
   Between services that you own, you MAY use gRPC.
2. Keep one source of truth for each API.\
   Generate the OpenAPI document from the code, or generate the code from the document.\
   Do not keep both by hand.
3. For gRPC, the `.proto` files are the source of truth.\
   Lint them with `buf lint`.\
   Generate code with `buf generate`.
4. Make the build stop with an error when a generated document or generated code is out of date.
5. Make the build stop with an error on a change that is not compatible with the current clients (`oasdiff breaking`, `buf breaking`).

- Add fields.\
  Remove a field only when no supported client uses it.
- In Protocol Buffers, do not use a field number again.\
  Reserve the number and the name of each removed field.
- Generate the client types from the contract.\
  Also parse each answer at runtime, because generated types do not examine data at runtime.
- Send HTTP errors as Problem Details (RFC 9457).\
  Send gRPC errors with a status code and details.
- Use the same status codes for errors in each API:

| Error | HTTP | gRPC |
| --- | --- | --- |
| The item is there already | 409 | `ALREADY_EXISTS` |
| The current state does not let the action occur | 409 | `FAILED_PRECONDITION` |
| The item changed after the client read it (a version conflict) | 409 | `ABORTED` |
| A deadlock or a serialization failure | 503 with `Retry-After` | `ABORTED` |
| Not found | 404 | `NOT_FOUND` |
| Forbidden | 403 | `PERMISSION_DENIED` |
| Not valid | 400 | `INVALID_ARGUMENT` |
| A lock timeout, or no free database connection | 503 with `Retry-After` | `UNAVAILABLE` |
