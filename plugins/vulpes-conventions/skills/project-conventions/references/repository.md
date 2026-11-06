# Repository

1. Put all apps of one product in one repository.\
   Put apps in `apps/`, and shared contracts and packages in `packages/`.
2. Give the root one command for each task: `build`, `dev`, `lint`, `check-types`, and `test`.
3. You SHOULD run the tasks with Turborepo and pnpm.\
   Give each app that is not JavaScript a `package.json` whose scripts run its own tools.\
   When the repository has no JavaScript app, you MAY use one Taskfile or Makefile at the root.
4. Keep the formatter and linter configuration in each app.\
   Keep shared TypeScript presets in `packages/typescript-config`.
5. Keep infrastructure code in `infra/`: compose files, Kubernetes manifests, and Terraform or OpenTofu code.
6. Write a `README.md` with the start steps, the folder layout, the generator commands, and the branch strategy ([git.md](git.md)).
7. Copy [agent-instructions.md](agent-instructions.md) to `docs/conventions/agent-instructions.md`.\
   Then write `AGENTS.md` and `CLAUDE.md` by its rules.

- In `turbo.json`, write the variables that change the build output in `env`, because they are part of the cache key.
- Write the variables that only `dev` reads in `passThroughEnv`.
- Let a package run its install scripts only when they are necessary (`allowBuilds` in `pnpm-workspace.yaml`).
