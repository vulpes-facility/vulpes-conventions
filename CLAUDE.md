# CLAUDE.md

A Claude Code plugin with one skill, `project-conventions`, that the `vulpes` marketplace (`vulpes-facility/claude-plugins`) points at with a `git-subdir` source.\
Read `README.md` before a change.\
The skill is written in ASD-STE100, with BCP 14 keywords and Semantic Line Breaks that show in the rendered output (a `\` at the end of each broken line).

## Index

- `README.md` - What the plugin does, how to install it, what each reference file covers, and how to change it.
- `plugins/vulpes-conventions/.claude-plugin/plugin.json` - The plugin manifest with its name, version, and description.
- `plugins/vulpes-conventions/skills/project-conventions/SKILL.md` - The skill entry point: rules for every task, the routing table to reference files, and the tool tables.
- `plugins/vulpes-conventions/skills/project-conventions/references/` - One file of rules for each topic, which Claude reads only when a task needs it.
- `LICENSE` - The MIT License of the repository.
