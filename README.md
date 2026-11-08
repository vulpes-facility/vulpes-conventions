# vulpes-conventions

A Claude Code plugin with general architecture and code conventions for software projects in any stack.\
Its skill, `project-conventions`, tells Claude how to set up a repository and how to add a service, an API, a migration, a screen, or a deployment.

## Install

```
claude plugin marketplace add vulpes-facility/claude-plugins
claude plugin install vulpes-conventions@vulpes
```

## Contents

`SKILL.md` keeps the rules for every task, the stack and component tool tables, and a table that tells which reference file to read for each task.\
Claude reads a reference file only when the task needs it.

| File | Rules for |
| --- | --- |
| `repository.md` | The monorepo layout and its root tasks |
| `agent-instructions.md` | `CLAUDE.md`, `AGENTS.md`, the project conventions in `docs/conventions/`, and the index format |
| `agent-sessions.md` | Messages between agent sessions: the message ID, the receipt of a remote session, and resends |
| `server-architecture.md` | Business modules and their four layers |
| `api-contract.md` | HTTP and gRPC contracts, compatibility checks, and error codes |
| `data-stores.md` | PostgreSQL, MongoDB, Redis or Valkey, and object storage |
| `messaging.md` | RabbitMQ, Kafka, and the transactional outbox |
| `client-apps.md` | Web, Flutter, Android, and iOS apps |
| `mobile-release.md` | Fastlane lanes and signing |
| `observability.md` | OpenTelemetry, logs, and alerts |
| `containers.md` | Dockerfiles and compose files |
| `kubernetes.md` | Deployments, probes, and Jobs |
| `servers.md` | Bare metal and virtual machines |
| `cloud.md` | AWS and OCI |
| `git.md` | Branch strategies, Conventional Commits, signed commits, and release-please |

The reference files are in [`plugins/vulpes-conventions/skills/project-conventions/references`](plugins/vulpes-conventions/skills/project-conventions/references).

## Development

1. Change the files under `plugins/vulpes-conventions`.
2. Try the plugin with `claude --plugin-dir plugins/vulpes-conventions`.
3. Run `claude plugin validate plugins/vulpes-conventions` before a pull request.

Follow the conventions in [`docs/conventions/`](docs/conventions/).

## License

[MIT](LICENSE)
