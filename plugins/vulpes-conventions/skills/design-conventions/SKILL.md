---
name: design-conventions
description: Design conventions for the user interface of web, mobile, and desktop apps. They start with a design brief for each service and with design principles, such as "less, but better" and usability heuristics. They help select a base design system. Examples are Material 3, Apple HIG, Fluent 2, GNOME HIG, IBM Carbon, Spectrum, Primer, Ant Design, Atlassian, Polaris, Salesforce Lightning, KRDS, GOV.UK, and USWDS. They cover tokens, color, typography, layout, input methods, components, motion, materials, UI text, and accessibility (WCAG 2.2). A glossary gives the names of patterns, such as hero animations. Use it when you design or review a screen, a flow, or a component, or make a wireframe, a mockup, or a prototype. Use it when you start the design of a service, select a design system, add a token or a theme, or write UI text. Use it when you adapt a UI to a platform, a browser, a window size, an input method, a language, or a user setting.
---

# Design conventions

This file uses ASD-STE100 (Simplified Technical English).\
MUST, MUST NOT, SHOULD, SHOULD NOT, and MAY are BCP 14 keywords (RFC 2119, RFC 8174).

## 1. Use of this file

1. Read the `AGENTS.md` and `README.md` of the project first.\
   Then read each file in `docs/conventions/` that the index of `AGENTS.md` lists for the task.\
   When the project has no `AGENTS.md`, read its `CLAUDE.md`.
2. Read `docs/conventions/design.md` of the project.\
   When the file or an item that the task needs is missing, ask the user by [`references/design-brief.md`](references/design-brief.md).\
   Write the answers in that file.
3. Before you do a task, read the reference files for it (section 3).
4. When two rules do not agree, use this order of priority, from the highest:\
   a. The decision of the user.\
   b. The rules of the project.\
   c. The rules in section 2 of this file.\
   d. On a native platform, the guideline of the platform for behavior: navigation, back, system dialogs, menus, keyboard shortcuts, text input, and permission requests.\
   e. The base design system.\
   f. The guideline of the platform for all other parts.\
   g. The reference files of this skill.
5. A project rule MAY lower a WCAG requirement when the project writes it in `docs/conventions/`.\
   A screen that does not meet WCAG is a defect, not a rule.\
   Before you apply such a rule, look for a design that meets the rule and WCAG together.\
   When there is none, apply the rule, and tell the user which WCAG criterion the result does not meet.\
   Write that criterion and the reason next to the project rule.
6. This skill does not decide which laws apply to the product.\
   The user and the project decide which accessibility standards the product meets ([`references/accessibility.md`](references/accessibility.md)).
7. This skill has design rules only.\
   It does not select a design tool, a token file format, or a technology.\
   For the code that builds a design, use the `project-conventions` skill and its `references/ui-implementation.md`.
8. Design systems and platform guidelines change with each major release.\
   When the version that the project uses is newer than your knowledge, read the current documents.

## 2. Rules for every task

1. Use the tokens and the components of the design system.\
   When none does the work, add one to the design system, not to one screen only.
2. Do not use raw values in screens and components.\
   Use a semantic or a component token for each color, size, space, radius, shadow, font, and duration ([`references/tokens.md`](references/tokens.md)).
3. On each platform, use the controls and the patterns of the platform for navigation, back, system dialogs, menus, keyboard shortcuts, and gestures.\
   Show the brand with tokens, icons, and images, not with changed controls.
4. Meet WCAG 2.2 level AA on each platform, also in native apps ([`references/accessibility.md`](references/accessibility.md)).
5. Design each state of each screen and each component: loading, empty, error, and the states in [`references/components.md`](references/components.md).\
   A design without these states is not complete.
6. Support the settings of the user: light and dark appearance, text size, contrast, reduced motion, and reduced transparency.
7. Adapt the UI to conditions, not to the names of devices.\
   The conditions are the platform, the window size, the container size, the input methods, the user settings, and the language.\
   A function MUST work without the newer features of a browser.
8. Use the same names for tokens and components in the design files and in the code.
9. Write the design decisions of the project in `docs/conventions/design.md`.\
   Use the template in [`references/design-brief.md`](references/design-brief.md).
10. Give the same function the same pattern, position, name, and icon on each screen.
11. When you write about a design, use the pattern names in [`references/glossary.md`](references/glossary.md).\
    When the user names a pattern with a different name, find it in that file, and use that pattern.
12. Less, but better: do not add an element that helps no main task of the service.\
    When the rules do not decide a case, use [`references/principles.md`](references/principles.md), and name the principle that you use.
13. Do not use deceptive patterns.\
    Examples are hidden costs, paid extras or consent that are selected for the user, and a cancel flow harder than the sign-up.\
    Also do not use false urgency, or text that shames the user for a refusal.

## 3. Reference files

Before you do a task in the left column, read each file in the right column.\
Read only the files that the task needs.

| Task | Read first |
| --- | --- |
| Start the design of a service, or select a base design system | [`references/design-brief.md`](references/design-brief.md), [`references/design-systems.md`](references/design-systems.md) |
| Set up a design system, add a token or a theme, or select colors or fonts | [`references/tokens.md`](references/tokens.md), [`references/color.md`](references/color.md), [`references/typography.md`](references/typography.md) |
| Design a screen, a flow, a component, or a form | [`references/layout.md`](references/layout.md), [`references/components.md`](references/components.md), [`references/input.md`](references/input.md), [`references/content.md`](references/content.md) |
| Design for a platform, or for more than one platform | [`references/platforms.md`](references/platforms.md) |
| Add motion, a transition, a material, or elevation | [`references/motion.md`](references/motion.md), [`references/materials.md`](references/materials.md) |
| Add icons, images, or an app icon | [`references/icons.md`](references/icons.md) |
| Write UI text, or add a language | [`references/content.md`](references/content.md) |
| Name a pattern, or find the pattern that the user names | [`references/glossary.md`](references/glossary.md) |
| Apply an accessibility standard that the user or the project names | [`references/accessibility.md`](references/accessibility.md) |
| Review a design or a built UI | [`references/principles.md`](references/principles.md), [`references/design-brief.md`](references/design-brief.md) (verification matrix), [`references/accessibility.md`](references/accessibility.md) |

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
