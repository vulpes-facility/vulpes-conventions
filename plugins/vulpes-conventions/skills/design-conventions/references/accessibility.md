# Accessibility

The minimum is WCAG 2.2 level AA on each platform (`SKILL.md`, section 2).\
For a native app, apply WCAG 2.2 with WCAG2ICT, and the accessibility guide of the platform.

1. Also check the criteria that WCAG 2.2 added at levels A and AA:\
   a. 2.4.11 Focus Not Obscured.\
   b. 2.5.7 Dragging Movements.\
   c. 2.5.8 Target Size.\
   d. 3.2.6 Consistent Help.\
   e. 3.3.7 Redundant Entry.\
   f. 3.3.8 Accessible Authentication.
2. Use the larger target size: the WCAG minimum or the size of the platform (`SKILL.md`, section 4).
3. Write the role, the name, the state, and the value of each control in the spec.
4. Give an accessibility action for each custom gesture.

## Laws and regional standards

1. When the user or the project names an accessibility standard, also meet that standard (`SKILL.md`, section 1).\
   Write the standard and its version in `docs/conventions/design.md`.
2. WCAG 2.2 level AA meets most web requirements of these standards, but not all of them.\
   Read the standard for its other requirements.
3. When the product must get an accessibility certificate, test it with the items of that standard.

| Region | Standard | Based on | Applies to |
| --- | --- | --- | --- |
| Korea | KWCAG 2.2 (한국형 웹 콘텐츠 접근성 지침) | WCAG 2.1 | Web content |
| Korea | KS X 3253 (모바일 애플리케이션 콘텐츠 접근성 지침) | Its own guidelines | Mobile apps |
| EU | EN 301 549 V4.1.1 | WCAG 2.2 A and AA | Web, software, mobile apps, and documents, under the European Accessibility Act and the Web Accessibility Directive |
| US | ADA Title II | WCAG 2.1 AA | Web content and mobile apps of state and local governments |
| US | Section 508 | WCAG 2.0 AA | Information technology of federal agencies |

KWCAG 2.2 is not WCAG 2.2.\
Only the version numbers are the same.\
Before you apply a standard, read its current version.

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
