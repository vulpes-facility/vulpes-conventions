# Design brief

Each service has its own requirements, and this skill cannot know them.\
The design brief is the set of decisions that each service makes.\
The answers go in `docs/conventions/design.md` of the project.

## Use

1. Before you design for a project, read its `docs/conventions/design.md`.
2. When you start the design of a service, ask the user each item of the kind "Ask".\
   For a later task, ask only the items that the task needs and that the file does not answer.
3. For an item of the kind "Default", tell the user the default.\
   Use the default when the user has no preference.
4. Write each answer in `docs/conventions/design.md`, in the form of the template.\
   Tell the user that you changed the file.
5. The rules in `SKILL.md`, section 2, are the floor for each service.\
   A default cannot go below them.\
   Only the user and the project can change them (`SKILL.md`, section 1).

## Items

| Item | Kind | Default | Rules |
| --- | --- | --- | --- |
| The kind of service, its main users, and their main tasks | Ask | None | All files |
| Target platforms | Ask | None | [`platforms.md`](platforms.md) |
| Base design system and its version | Ask | A recommendation only | [`design-systems.md`](design-systems.md) |
| Brand: colors, fonts, logo, and illustration style | Ask | The values of the base design system | [`tokens.md`](tokens.md), [`color.md`](color.md), [`typography.md`](typography.md), [`icons.md`](icons.md) |
| Languages, and right-to-left scripts | Ask | The language of the user only | [`content.md`](content.md) |
| Supported browsers | Default | The browsers that the project supports for its code | `SKILL.md`, section 2 |
| Window sizes | Default | All window size classes, from compact | [`layout.md`](layout.md) |
| Input methods | Default | A pointer, touch, and a keyboard | [`input.md`](input.md) |
| Density | Default | The density of the base design system | [`tokens.md`](tokens.md) |
| Motion | Default | Standard: springs with no bounce | [`motion.md`](motion.md) |
| Themes | Default | Light and dark, by the system setting | [`color.md`](color.md) |
| Formality and capitalization | Default | One level of formality for each language, and the capitalization of the platform | [`content.md`](content.md) |
| Design principles | Default | Less, but better, and the usability heuristics | [`principles.md`](principles.md) |
| Accessibility | Floor | WCAG 2.2 level AA | [`accessibility.md`](accessibility.md) |
| Accessibility standards that a law names | Only when the user names one | None | [`accessibility.md`](accessibility.md) |
| Verification matrix | Made from the items above | See Verification matrix | This file |

## Verification matrix

1. Make the matrix from the target platforms, the browsers, the window sizes, and the input methods.
2. Do not test each combination.\
   Test the ends of each axis, and the tests in [`accessibility.md`](accessibility.md):\
   a. The smallest window with touch.\
   b. The largest window with a pointer and a keyboard.\
   c. Each target platform.\
   d. Each browser engine of the supported browsers, and the oldest supported version.\
   e. Each language direction that the product supports.
3. Before you report a design or a UI as complete, check it in each row of the matrix.\
   When you cannot check a row, tell the user which rows you did not check.

## Template

```markdown
# Design

## Service

- Kind:
- Main users:
- Main tasks:
- Design principles:

## Targets

- Platforms:
- Browsers:
- Window sizes:
- Input methods:

## Design system

- Base design system and version:
- Brand:
- Density:
- Motion:
- Themes:

## Content

- Languages:
- Formality and capitalization:

## Accessibility

- Standards:
- Exceptions: each project rule that lowers a WCAG requirement, with the criterion and the reason.

## Verification matrix

| Row | Platform | Browser | Window | Input | Settings |
| --- | --- | --- | --- | --- | --- |

## Rules

- Each project rule that differs from the design-conventions skill.
```
