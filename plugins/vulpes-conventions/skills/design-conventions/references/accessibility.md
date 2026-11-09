# Accessibility

The minimum is WCAG 2.2 level AA on each platform.\
For a native app, apply WCAG 2.2 with WCAG2ICT, and the accessibility guide of the platform.

## Checks

| Area | Requirement | WCAG |
| --- | --- | --- |
| Text alternatives | Each image with information has a text alternative | 1.1.1 |
| Media | Prerecorded audio has a transcript, and videos have captions and an audio description | 1.2.1, 1.2.2, 1.2.3, 1.2.5 |
| Structure | Headings, lists, tables, and landmarks are in the code, not only in the look | 1.3.1 |
| Orientation | The UI works in both orientations | 1.3.4 |
| Color | Color is not the only way to show information | 1.4.1 |
| Contrast | Text has 4.5:1, large text 3:1, and UI parts 3:1 | 1.4.3, 1.4.11 |
| Text size | Text at 200% loses no content and no function | 1.4.4 |
| Reflow | Content works at 320 CSS px width | 1.4.10 |
| Text spacing | The layout works with more text spacing | 1.4.12 |
| Hover and focus content | The user can close it, move to it, and keep it | 1.4.13 |
| Keyboard | Each function works with a keyboard, and the focus can always move out | 2.1.1, 2.1.2 |
| Character key shortcuts | The user can turn off or change each shortcut of one character key | 2.1.4 |
| Time limits | The user can stop or extend each time limit | 2.2.1 |
| Moving content | Motion that starts by itself and lasts more than 5 seconds can be paused | 2.2.2 |
| Flashes | No content flashes more than 3 times in one second | 2.3.1 |
| Focus | The focus order is logical, and the focus is visible and not hidden | 2.4.3, 2.4.7, 2.4.11 |
| Gestures | Each path or multi-finger gesture, and each drag, has a single-pointer alternative | 2.5.1, 2.5.7 |
| Pointer cancellation | The action occurs when the pointer goes up, and the user can cancel it | 2.5.2 |
| Label in name | The accessible name contains the visible label | 2.5.3 |
| Target size | Targets are at least 24 × 24 CSS px | 2.5.8 |
| Language | The language of the page or the app is set | 3.1.1 |
| Consistent navigation | Navigation that repeats on screens is in the same order on each screen | 3.2.3 |
| Consistent identification | Elements with the same function have the same name and icon on each screen | 3.2.4 |
| Consistent help | Help is in the same place on each screen | 3.2.6 |
| Errors | Errors are shown in text, with a fix when one is known | 3.3.1, 3.3.3 |
| Authentication | Sign-in does not need a memory test or a puzzle | 3.3.8 |
| Name, role, value | Each control gives its name, role, state, and value to assistive technology | 4.1.2 |
| Status messages | Assistive technology tells status messages without a focus change | 4.1.3 |

The target sizes of the platforms are larger than the WCAG minimum (`SKILL.md`, section 4).\
Use the larger size.

## Laws and regional standards

1. When the user or the project names an accessibility standard, also meet that standard (`SKILL.md`, section 1).\
   The table below shows some standards that laws name.
2. Write each standard and its version in the design conventions of the project (`SKILL.md`, section 2).
3. WCAG 2.2 level AA meets most web requirements of these standards, but not all of them.\
   Read the standard for its requirements outside the web, and for the items that it checks in a different way.
4. When the product must get an accessibility certificate, test it with the items of that standard.

| Region | Standard | Based on | Applies to |
| --- | --- | --- | --- |
| Korea | KWCAG 2.2 (한국형 웹 콘텐츠 접근성 지침) | WCAG 2.1 | Web content |
| Korea | KS X 3253 (모바일 애플리케이션 콘텐츠 접근성 지침) | Its own guidelines | Mobile apps |
| EU | EN 301 549 V4.1.1 | WCAG 2.2 A and AA | Web, software, mobile apps, and documents, under the European Accessibility Act and the Web Accessibility Directive |
| US | ADA Title II | WCAG 2.1 AA | Web content and mobile apps of state and local governments |
| US | Section 508 | WCAG 2.0 AA | Information technology of federal agencies |

KWCAG 2.2 is not WCAG 2.2.\
Only the version numbers are the same.\
The versions and the dates of these standards change.\
Before you apply a standard, read its current version.

## Screen readers

1. Write the role, the name, the state, and the value of each control in the spec.\
   The code gives them to assistive technology.
2. Write names that tell the action or the content, for example "Delete photo".\
   Do not use names such as "Button", "Icon", or "Image".
3. Group elements that the user reads as one, for example the parts of a card.
4. Mark decorative images as decorative, so that the screen reader does not read them.
5. For each custom gesture, give an accessibility action.

## Tests

1. Test each new screen and each new component with:\
   a. A keyboard only.\
   b. The screen reader of each platform (`SKILL.md`, section 4).\
   c. The largest text size of the platform.\
   d. The dark theme and the high-contrast settings.\
   e. Reduced motion and reduced transparency.\
   f. A width of 320 CSS px on the web.
2. Automatic checkers find only some of the problems.\
   Use them, and also test by hand.
