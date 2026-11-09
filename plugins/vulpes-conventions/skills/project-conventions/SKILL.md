---
name: project-conventions
description: Architecture and code conventions for software projects in any stack. The code stacks include Go, Java or Kotlin with Spring Boot, TypeScript with NestJS, React, Vue, and Flutter. They also include Swift for iOS, Kotlin for Android, OpenAPI, and gRPC. The components include PostgreSQL, MongoDB, Redis or Valkey, RabbitMQ, Kafka, S3-compatible storage, OpenTelemetry, and Fastlane. Use it when you set up a repository or add an app, a service, or a component. Use it when you write AGENTS.md, CLAUDE.md, or a project convention. Use it when you add a module, a screen, an API, a message, a migration, or an environment variable. Use it when you write a Dockerfile, a compose file, or Kubernetes manifests. Use it when you set up a server, or cloud resources on AWS or OCI. Use it when you make a branch, a commit, a pull request, or a release.
---

# Project conventions

This file uses ASD-STE100 (Simplified Technical English).\
MUST, MUST NOT, SHOULD, SHOULD NOT, and MAY are BCP 14 keywords (RFC 2119, RFC 8174).

## 1. Use of this file

1. Read the `AGENTS.md` and `README.md` of the project first.\
   Then read each file in `docs/conventions/` that the index of `AGENTS.md` lists for the task.\
   When the project has no `AGENTS.md`, read its `CLAUDE.md`.\
   A project rule MUST have priority over a rule in this file and in its reference files.\
   The decision of the user MUST have priority over a project rule and over the rules in this file and in its reference files.
2. Find the stack of each app in section 4.\
   Find each component in section 5.
3. Apply the rules in section 2 to each task.
4. Before you do a task, read the reference files for that task (section 3).\
   Apply their rules with the tools in sections 4 and 5.
5. When a stack or a component is not in the tables, use its official tools and its official architecture guide.
6. When the installed version of a tool is newer than your knowledge, read the docs of the installed version.
7. Pin the tool versions in the project.\
   This file does not pin them.

## 2. Rules for every task

1. Make each file with a generator.\
   Write a file by hand only when no generator makes it.
2. Add a dependency with the package manager of the app.\
   Do not edit the lockfile by hand.
3. Format with the official formatter of the language.\
   The linter MUST show no errors and no warnings.
4. Write doc comments only on code that callers use (JSDoc, Go doc comments, Javadoc, KDoc, DocC, dartdoc).\
   For each state, tell the result: the return value, the refusal, or the side effect.\
   Do not write the name again in other words.
5. Read the server configuration from environment variables.\
   Validate it at startup.\
   Stop the process when a value is not correct.
6. Do not put secrets in the repository or in a client app.\
   Write each variable in `.env.example`.
7. Do not put sample data or stub paths in product code.\
   Keep them in the test tools.
8. Keep instants in UTC.\
   Send them as RFC 3339 text with `Z`, or as `google.protobuf.Timestamp`.\
   Show local time only on the screen.
9. Write each commit message and each pull request title in the Conventional Commits form: `<type>(<scope>): <description>`.\
   Make branches and merges by the branch strategy of the project ([`references/git.md`](references/git.md)).
10. Do not commit or push unless the user asks.\
    Before you report work as done, run the build, lint, type check, and tests of each changed app.

## 3. Reference files

Before you do a task in the left column, read each file in the right column.\
One task can match more than one row.\
Read only the files that the task needs.

| Task | Read first |
| --- | --- |
| Set up a repository | [`references/repository.md`](references/repository.md), [`references/agent-instructions.md`](references/agent-instructions.md), [`references/git.md`](references/git.md) |
| Write `AGENTS.md`, `CLAUDE.md`, or a project convention | [`references/agent-instructions.md`](references/agent-instructions.md) |
| Send a message to another agent session, or receive one | [`references/agent-sessions.md`](references/agent-sessions.md) |
| Add an app | [`references/repository.md`](references/repository.md) |
| Add a service, a module, or a use case | [`references/server-architecture.md`](references/server-architecture.md), [`references/api-contract.md`](references/api-contract.md) |
| Add or change an HTTP or gRPC API | [`references/api-contract.md`](references/api-contract.md) |
| Add a data store, a query, a schema change, or a migration | [`references/data-stores.md`](references/data-stores.md), and the deploy file |
| Add a broker, a message, a publisher, or a consumer | [`references/messaging.md`](references/messaging.md) |
| Add a client app or a screen | [`references/client-apps.md`](references/client-apps.md), [`references/ui-implementation.md`](references/ui-implementation.md) |
| Build a design in code: tokens, conditions, semantics, motion, or localization | [`references/ui-implementation.md`](references/ui-implementation.md) |
| Release a mobile app, or set up signing | [`references/mobile-release.md`](references/mobile-release.md) |
| Add traces, metrics, logs, alerts, or dashboards | [`references/observability.md`](references/observability.md) |
| Write a Dockerfile or a compose file | [`references/containers.md`](references/containers.md) |
| Write Kubernetes manifests | [`references/kubernetes.md`](references/kubernetes.md) |
| Set up a server without Kubernetes | [`references/servers.md`](references/servers.md) |
| Add cloud resources on AWS or OCI | [`references/cloud.md`](references/cloud.md) |
| Make a branch, a commit, a pull request, or a release | [`references/git.md`](references/git.md) |
| Add an environment variable | [`references/repository.md`](references/repository.md), the deploy file, [`references/client-apps.md`](references/client-apps.md) for a client app, [`references/cloud.md`](references/cloud.md) for a secret |

The deploy file is the file for the place where the app runs:\
[`references/containers.md`](references/containers.md) for compose,\
[`references/kubernetes.md`](references/kubernetes.md) for Kubernetes,\
or [`references/servers.md`](references/servers.md) for bare metal and virtual machines.

## 4. Stack tools

| Stack | Generator | Format and lint | Architecture check | Migrations | Tests |
| --- | --- | --- | --- | --- | --- |
| Go | `go mod init`, folders `cmd/<app>` and `internal/<module>` | `gofmt`, `go vet`, `golangci-lint` | `depguard` in `golangci-lint` | `goose`, or `migrate` (golang-migrate) | `go test`, Testcontainers |
| Java or Kotlin, Spring Boot | Spring Initializr, Gradle | Spotless, Error Prone (Java), ktlint or detekt (Kotlin) | Spring Modulith `verify()`, ArchUnit | Flyway | JUnit (the version that Spring Boot manages), Testcontainers |
| TypeScript, NestJS | `nest new`, `nest g` | Prettier, oxlint or ESLint | dependency-cruiser | node-pg-migrate | Vitest, supertest |
| React | `create-vite` (`react-compiler-ts`), `fsd` CLI, `shadcn` when the design system has no React library | Prettier, ESLint | steiger | none | Vitest, Playwright |
| Vue | `create-vue`, `fsd` CLI | Prettier, ESLint | steiger | none | Vitest, Playwright |
| Flutter | `flutter create` | `dart format`, `flutter analyze` | a test that reads the imports | none | `flutter test`, `integration_test` |
| Android (Kotlin) | Android Studio template, Gradle | ktlint, Android Lint, detekt | Gradle modules, a test of the module graph | Room migrations | JUnit, Compose UI tests |
| iOS (Swift) | Xcode template, Swift Package Manager | `swift-format`, SwiftLint | Swift Package Manager targets, a test of the package graph | SwiftData `SchemaMigrationPlan` | Swift Testing, XCTest, XCUITest |
| gRPC | `buf config init` | `buf format`, `buf lint` | `buf breaking` | none | none |
| OpenAPI | generate from code, or write first | Spectral or Redocly CLI | `oasdiff breaking` | none | none |

## 5. Component tools

| Component | Contract or schema | Changes as code | Local run | Tests |
| --- | --- | --- | --- | --- |
| PostgreSQL | SQL migrations | Flyway or the stack tool | Official image in compose | Testcontainers |
| MongoDB | `$jsonSchema` validators | migrate-mongo, Mongock, golang-migrate | Official image as a one-node replica set | Testcontainers |
| Redis or Valkey | Key names and expiry times | none | Official image in compose | Testcontainers |
| RabbitMQ | AsyncAPI | Definitions file (queues, exchanges, bindings) | Official image with the management plugin | Testcontainers |
| Kafka | AsyncAPI, schema registry | Topic settings as code | Official `apache/kafka` image in KRaft mode | Testcontainers |
| S3-compatible storage | Bucket names | A one-shot bucket setup | SeaweedFS or Garage | The same image |
| OpenTelemetry | Semantic conventions | Collector settings as code | `grafana/otel-lgtm` for development | none |
| Fastlane | `Fastfile` lanes | `Appfile`, `Matchfile` | none | the `test` lane |
