---
name: design-conventions
description: Design conventions for the user interface of web, mobile, and desktop apps. They cover a design brief for each service, design principles such as "less, but better" and usability heuristics, the selection of a base design system (Material 3, Apple HIG, Fluent 2, GNOME HIG, IBM Carbon, Spectrum, Primer, Ant Design, Atlassian, Polaris, Salesforce Lightning, KRDS, GOV.UK, USWDS), tokens, color, typography, layout, input methods, components, motion, materials such as Liquid Glass, UI text, accessibility (WCAG 2.2), and a glossary of pattern names such as hero animations. Use it when you design or review a screen, a flow, or a component, or make a wireframe, a mockup, or a prototype. Use it when you start the design of a service, select a design system, add a token or a theme, or write UI text. Use it when you adapt a UI to a platform, a browser, a window size, an input method, a language, or a user setting.
---

# Design conventions

This file uses ASD-STE100 (Simplified Technical English).\
MUST, MUST NOT, SHOULD, SHOULD NOT, and MAY are BCP 14 keywords (RFC 2119, RFC 8174).

## 1. Use of this file

1. Read the `AGENTS.md` and `README.md` of the project first.\
   Then read each file in `docs/conventions/` that the index of `AGENTS.md` lists for the task.\
   When the project has no `AGENTS.md`, read its `CLAUDE.md`.\
   A project rule MUST have priority over a rule in this file and in its reference files.
2. Read `docs/conventions/design.md` of the project.\
   When the file or an item that the task needs is missing, ask the user by [`references/design-brief.md`](references/design-brief.md).\
   Write the answers in that file.
3. Find the target platforms in `docs/conventions/design.md`.\
   Section 4 gives the facts of each platform.
4. Apply the rules in section 2 to each task.
5. Before you do a task, read the reference files for that task (section 3).
6. When two rules do not agree, use this order of priority, from the highest:\
   a. The decision of the user.\
   b. The rules of the project (rule 1).\
   c. The rules in section 2 of this file.\
   d. On a native platform, the guideline of the platform for behavior: navigation, back, system dialogs, menus, keyboard shortcuts, text input, and permission requests.\
   e. The base design system.\
   f. The guideline of the platform for all other parts.\
   g. The reference files of this skill.
7. A project rule MAY lower a WCAG requirement when the project writes it in `docs/conventions/`.\
   A screen that does not meet WCAG is a defect, not a rule.\
   Before you apply such a rule, look for a design that meets the rule and WCAG together.\
   When there is none, apply the rule, and tell the user which WCAG criterion the result does not meet.\
   Write that criterion and the reason next to the project rule.
8. This skill does not decide which laws apply to the product.\
   The user and the project decide which accessibility standards the product meets ([`references/accessibility.md`](references/accessibility.md)).
9. This skill has design rules only.\
   It does not select a design tool, a token file format, or a technology.\
   For the code that builds a design, use the `project-conventions` skill and its `references/ui-implementation.md`.
10. Design systems and platform guidelines change with each major release.\
    When the version that the project uses is newer than your knowledge, read the current documents.

## 2. Rules for every task

1. Use the tokens and the components of the design system.\
   Before you add a component, a token, or a pattern, look for one that does the same work.\
   When none does, add it to the design system, not to one screen only.
2. Do not use raw values in screens and components.\
   Use a semantic token for each color, size, space, radius, shadow, font, and duration ([`references/tokens.md`](references/tokens.md)).
3. On each platform, use the controls and the patterns of the platform for navigation, back, system dialogs, menus, keyboard shortcuts, and gestures.\
   Show the brand with tokens, icons, and images, not with changed controls.
4. Meet WCAG 2.2 level AA on each platform, also in native apps ([`references/accessibility.md`](references/accessibility.md)).
5. Design each state of each screen and each component: loading, empty, error, and the states in [`references/components.md`](references/components.md).\
   A design without these states is not complete.
6. Support the settings of the user: light and dark appearance, text size, contrast, reduced motion, and reduced transparency.
7. Adapt the UI to conditions, not to the names of devices.\
   Section 5 gives the conditions and where each condition is decided.
8. Design for each language that the product supports ([`references/content.md`](references/content.md)).
9. Use the same names for tokens and components in the design files and in the code.
10. Write the design decisions of the project in `docs/conventions/design.md`.\
    Use the template in [`references/design-brief.md`](references/design-brief.md).
11. Keep the product consistent.\
    Give the same function the same pattern, position, name, and icon on each screen (WCAG 3.2.3, 3.2.4).\
    The design system gives the parts, but only their use on each screen makes the product consistent.
12. When you write about a design, use the pattern names in [`references/glossary.md`](references/glossary.md).\
    When the user names a pattern with a different name, find it in that file, and use that pattern.
13. Less, but better: do not add an element that helps no main task of the service.\
    When the rules do not decide a case, use [`references/principles.md`](references/principles.md), and name the principle that you use.

## 3. Reference files

Before you do a task in the left column, read each file in the right column.\
One task can match more than one row.\
Read only the files that the task needs.

| Task | Read first |
| --- | --- |
| Start the design of a service, or find that `docs/conventions/design.md` does not answer an item | [`references/design-brief.md`](references/design-brief.md), [`references/design-systems.md`](references/design-systems.md) |
| Select a base design system, or change it | [`references/design-systems.md`](references/design-systems.md), [`references/platforms.md`](references/platforms.md) |
| Set up a design system, or add or change a token | [`references/tokens.md`](references/tokens.md), [`references/color.md`](references/color.md), [`references/typography.md`](references/typography.md) |
| Select colors, or add a theme | [`references/color.md`](references/color.md), [`references/tokens.md`](references/tokens.md) |
| Select fonts, or make a type scale | [`references/typography.md`](references/typography.md) |
| Design a screen or a flow | [`references/layout.md`](references/layout.md), [`references/components.md`](references/components.md), [`references/content.md`](references/content.md), [`references/platforms.md`](references/platforms.md) |
| Make a layout adapt to window sizes | [`references/layout.md`](references/layout.md) |
| Support an input method: a pointer, touch, a keyboard, or a pen | [`references/input.md`](references/input.md) |
| Design or change a component | [`references/components.md`](references/components.md), [`references/accessibility.md`](references/accessibility.md) |
| Design a form | [`references/components.md`](references/components.md), [`references/content.md`](references/content.md) |
| Add icons, images, illustrations, or an app icon | [`references/icons.md`](references/icons.md) |
| Add motion or a transition | [`references/motion.md`](references/motion.md), [`references/glossary.md`](references/glossary.md) |
| Add a translucent material, a blur, elevation, or a scrim | [`references/materials.md`](references/materials.md) |
| Name a pattern, or find the pattern that the user names (for example a hero animation or a bento grid) | [`references/glossary.md`](references/glossary.md) |
| Write labels, messages, or other UI text | [`references/content.md`](references/content.md) |
| Add a language, or a right-to-left script | [`references/content.md`](references/content.md), [`references/layout.md`](references/layout.md) |
| Design for a platform or a browser, or for more than one platform | [`references/platforms.md`](references/platforms.md) |
| Apply an accessibility standard that the user or the project names, for example KWCAG or EN 301 549 | [`references/accessibility.md`](references/accessibility.md) |
| Decide a case that the rules do not cover | [`references/principles.md`](references/principles.md) |
| Review a design or a built UI | [`references/principles.md`](references/principles.md) (usability heuristics), [`references/design-brief.md`](references/design-brief.md) (verification matrix), [`references/accessibility.md`](references/accessibility.md), [`references/components.md`](references/components.md), and the files for the parts that it changes |

## 4. Platforms

| Platform | Guideline | System font | Main navigation | Target size | Text size setting | Screen reader |
| --- | --- | --- | --- | --- | --- | --- |
| Web | The base design system | The system font of each operating system, or the font of the design system | Top bar or side bar, by window size | 24 × 24 CSS px at least, 44 × 44 for touch | Browser font size and zoom | NVDA, JAWS, VoiceOver, TalkBack |
| iOS, iPadOS | Apple HIG | SF Pro | Tab bar, navigation stack, sidebar on iPad | 44 × 44 pt | Dynamic Type | VoiceOver |
| Android | Material 3 | Roboto, or the font of the design system | Navigation bar, navigation rail | 48 × 48 dp | Font size, to 200% | TalkBack |
| macOS | Apple HIG | SF Pro | Menu bar, toolbar, sidebar | 28 × 28 pt | Text size in Accessibility settings | VoiceOver |
| Windows | Fluent 2 | Segoe UI Variable | Navigation view (left or top), command bar | 40 × 40 epx | Text size in Accessibility settings | Narrator, NVDA, JAWS |
| Linux (GNOME) | GNOME HIG | Adwaita Sans (GNOME 48 and later) | Header bar, sidebar, view switcher | The sizes of the libadwaita widgets | Large Text, text scaling factor | Orca |

The target size is the size of the area that takes the input.\
The visible part of a control can be smaller.

## 5. Conditions

| Condition | Decided by | Rules |
| --- | --- | --- |
| Platform | The platform guideline | [`references/platforms.md`](references/platforms.md) |
| Browser | The browsers that the project supports. A function MUST work without the newer features of a browser | [`references/platforms.md`](references/platforms.md) |
| Window size | The window size class, and the size of the container | [`references/layout.md`](references/layout.md) |
| Pixel density | Units that do not depend on the density, and images for each density | [`references/tokens.md`](references/tokens.md), [`references/icons.md`](references/icons.md) |
| Input method | The input capabilities, not the device | [`references/input.md`](references/input.md) |
| User settings | The settings of the system | [`references/color.md`](references/color.md), [`references/typography.md`](references/typography.md), [`references/motion.md`](references/motion.md), [`references/materials.md`](references/materials.md) |
| Language | The locale | [`references/content.md`](references/content.md) |
