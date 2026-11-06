# vulpes-conventions

A Claude Code plugin with the architecture and code conventions of vulpes-facility, for software projects in any stack.\
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
| `git.md` | Branch strategies, Conventional Commits, and release-please |

The reference files are in [`plugins/vulpes-conventions/skills/project-conventions/references`](plugins/vulpes-conventions/skills/project-conventions/references).

## Development

1. Change the files under `plugins/vulpes-conventions`.
2. Try the plugin with `claude --plugin-dir plugins/vulpes-conventions`.
3. Run `claude plugin validate plugins/vulpes-conventions` before a pull request.

- Write each commit message and each pull request title as a Conventional Commit.
- Merge pull requests with a squash merge.
- Write the skill in ASD-STE100 (Simplified Technical English), with BCP 14 keywords and Semantic Line Breaks.

## License

[MIT](LICENSE)
