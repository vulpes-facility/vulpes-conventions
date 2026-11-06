# Server architecture

Use this file for each server, in any language.\
Divide the code into business modules, and each module into four layers.

| Layer | Contents |
| --- | --- |
| `domain` | Aggregates, value objects, domain events, repository contracts, domain errors |
| `application` | One method for each use case, query contracts, response types, event handlers |
| `infrastructure` | Repository and query implementations, database code, message publishers and consumers, adapters |
| `interface` | HTTP handlers or gRPC services, request types, guards |

1. In Go, Java, and Kotlin, `interface` is a reserved word.\
   In those languages, name that layer `transport`.
2. Dependencies MUST point inward.\
   `domain` MUST NOT import a framework, a database driver, a message client, HTTP types, the clock, or random values.
3. `application` and `interface` MUST NOT import `infrastructure`.
4. Connect a contract to its implementation only in the composition root (Nest module file, Spring `@Configuration`, Go `main`).
5. Another module MUST use a module only through its public API: `index.ts`, an exported Go package, or a Spring Modulith API package.
6. A module writes only its own tables, collections, keys, and topics.\
   It gets the data of another module through the public API of that module.\
   It can also use the events that the other module publishes.
7. Modules MUST NOT have dependency cycles.\
   To tell a module about a change in the other direction, use an event.
8. Do a check of these rules with the architecture tool of the stack (Stack tools in `SKILL.md`).\
   Keep one example that breaks each rule.\
   Keep a test that makes sure that the tool refuses each example.
9. Do not rate-limit requests in the server.\
   Do not serve the web build from the server.\
   The gateway and a web server do these tasks.
