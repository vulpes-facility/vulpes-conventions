# AGENTS.md

A Claude Code plugin with one skill, `project-conventions`, that the `vulpes` marketplace (`vulpes-facility/claude-plugins`) points at with a `git-subdir` source.\
The skill gives general architecture and code conventions to Claude, for software projects in any stack.

## Index

- `README.md` - What the plugin does, how to install it, what each reference file covers, and how to change it.
- `docs/conventions/agent-instructions.md` - The rules for `CLAUDE.md`, `AGENTS.md`, `docs/conventions/`, and the format of each index.
- `docs/conventions/writing.md` - How to write the skill and the documents: English, ASD-STE100, BCP 14 keywords, and Semantic Line Breaks.
- `docs/conventions/pull-requests.md` - Commit messages, pull request descriptions, task issues, the merge method, and the plugin version.
- `plugins/vulpes-conventions/.claude-plugin/plugin.json` - The plugin manifest with its name, version, and description.
- `plugins/vulpes-conventions/skills/project-conventions/SKILL.md` - The skill entry point: rules for every task, the routing table to reference files, and the tool tables.
- `plugins/vulpes-conventions/skills/project-conventions/references/` - One file of rules for each topic, which Claude reads only when a task needs it.
- `LICENSE` - The MIT License of the repository.
