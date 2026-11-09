# vulpes-conventions

A Claude Code plugin with general architecture, code, and design conventions for software projects in any stack.\
Its skill `project-conventions` tells Claude how to set up a repository and how to add a service, an API, a migration, a screen, or a deployment.\
Its skill `design-conventions` tells Claude how to design the user interface of web, mobile, and desktop apps.

## Install

```
claude plugin marketplace add vulpes-facility/claude-plugins
claude plugin install vulpes-conventions@vulpes
```

## Contents

Each `SKILL.md` keeps the rules for every task, the tool or platform tables, and a table that tells which reference file to read for each task.\
Claude reads a reference file only when the task needs it.

### project-conventions

| File | Rules for |
| --- | --- |
| `repository.md` | The monorepo layout and its root tasks |
| `agent-instructions.md` | `CLAUDE.md`, `AGENTS.md`, the project conventions in `docs/conventions/`, and the index format |
| `agent-sessions.md` | Messages between agent sessions: the message ID, the receipt of a remote session, and resends |
| `server-architecture.md` | Business modules and their four layers |
| `api-contract.md` | HTTP and gRPC contracts, compatibility checks, and error codes |
| `data-stores.md` | PostgreSQL, MongoDB, Redis or Valkey, and object storage |
| `messaging.md` | RabbitMQ, Kafka, and the transactional outbox |
| `client-apps.md` | Web, Flutter, Android, iOS, Electron, Tauri, and egui apps |
| `ui-implementation.md` | How to build the design of `design-conventions` in code: component libraries, tokens, conditions, browsers, semantics, motion, and localization |
| `mobile-release.md` | Fastlane lanes and signing |
| `testing.md` | Which tests not to write, regression tests for bug fixes, test doubles, and failing tests |
| `desktop-release.md` | The release decisions of the project, CI packaging, signing, and updates of desktop apps |
| `observability.md` | OpenTelemetry, logs, and alerts |
| `containers.md` | Dockerfiles and compose files |
| `kubernetes.md` | Deployments, probes, and Jobs |
| `servers.md` | Bare metal and virtual machines |
| `cloud.md` | AWS and OCI |
| `git.md` | Branch strategies, Conventional Commits, signed commits, and release-please |

The reference files are in [`plugins/vulpes-conventions/skills/project-conventions/references`](plugins/vulpes-conventions/skills/project-conventions/references).

### design-conventions

The skill has design rules only, and no code rules.\
It does not select a design tool, a token file format, or a technology.\
The project selects a base design system, for example Material 3, Fluent 2, or IBM Carbon, and the skill applies its rules with that design system.

| File | Rules for |
| --- | --- |
| `design-brief.md` | The decisions of each service, their defaults, the verification matrix, and the template of `docs/conventions/design.md` |
| `principles.md` | Less, but better, usability heuristics for reviews, and principles for cases that rules do not cover |
| `design-systems.md` | The selection and the use of a base design system, and custom design systems |
| `tokens.md` | Token tiers, names, scales, themes, and the source of the tokens |
| `color.md` | Color roles, contrast checks, color scales, and dark and high-contrast themes |
| `typography.md` | Fonts, type scales, text size settings, and readability |
| `layout.md` | Window size classes, space, system areas, and right-to-left layouts |
| `input.md` | Hover, context menus, shortcuts, touch targets, and gestures, by input capability |
| `components.md` | Component specs, states, actions, feedback, screen states, and forms |
| `accessibility.md` | The criteria that WCAG 2.2 added, the standards that laws name, and accessibility tests |
| `motion.md` | Springs, durations, transitions, and reduced motion |
| `materials.md` | Translucent materials such as Liquid Glass, Mica, and Acrylic, reduced transparency, and elevation |
| `icons.md` | Icon sets, images, and app icons |
| `content.md` | UI text, labels, messages, and localization |
| `platforms.md` | Platform rules that agents often miss, and the differences between platforms |
| `glossary.md` | The names of patterns on each platform, and names with more than one meaning |

The reference files are in [`plugins/vulpes-conventions/skills/design-conventions/references`](plugins/vulpes-conventions/skills/design-conventions/references).

## Development

1. Change the files under `plugins/vulpes-conventions`.
2. Try the plugin with `claude --plugin-dir plugins/vulpes-conventions`.
3. Run `claude plugin validate plugins/vulpes-conventions` before a pull request.

Follow the conventions in [`docs/conventions/`](docs/conventions/).

## License

[MIT](LICENSE)
