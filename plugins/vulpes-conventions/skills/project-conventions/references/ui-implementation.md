# UI implementation

These rules tell how to build in code the design that the `design-conventions` skill gives.\
The design rules stay in that skill.

## Component libraries

[`client-apps.md`](client-apps.md) tells when to use the official component library of the base design system.\
This table gives the official components of each design system.

| Design system | Official components |
| --- | --- |
| Apple HIG | SwiftUI, UIKit, AppKit |
| Material 3 | Jetpack Compose Material 3, Flutter Material. On the web, Material Web is in maintenance mode |
| Fluent 2 | WinUI 3, Fluent UI React, Fluent UI Web Components |
| GNOME HIG | GTK 4, libadwaita |
| IBM Carbon | `@carbon/react`, `@carbon/web-components` |
| Adobe Spectrum | React Spectrum, Spectrum Web Components |
| Primer | `@primer/react` |
| Ant Design | `antd` |
| Atlassian Design System | `@atlaskit` packages, Forge UI Kit |
| Shopify Polaris | Polaris web components (Polaris React is deprecated) |
| Salesforce Lightning Design System | Lightning base components |
| KRDS | The code on `krds.go.kr` |
| GOV.UK Design System | `govuk-frontend` |
| USWDS | `@uswds/uswds` |

1. For a custom design system, build the components on a component library with accessible behavior, and give them the tokens of the design system.\
   On React, use shadcn (`SKILL.md`, section 4).

## Tokens

1. Make the token files of each platform from the token source in the repository with a tool.\
   Do not edit the made files by hand.
2. Keep the words of each token name, and change only the form for each platform.\
   For example, use `--color-text-primary` in CSS and `colorTextPrimary` in Swift and Kotlin.
3. On the web, write font sizes in `rem`, and line heights with no unit.\
   Then the font size setting of the browser changes them.

## Conditions

Detect each condition itself.\
Do not detect a device or a browser by its name or its user agent.

| Condition | Web | Native platforms |
| --- | --- | --- |
| Browser features | `@supports`, and feature detection in scripts | None |
| Window size | Media queries, and container queries for the size of a component | Size classes (Apple), window size classes (Android), breakpoints (libadwaita) |
| Input | `pointer` and `hover` for the primary input, `any-pointer` and `any-hover` for all inputs | The input events and the pointer effects of the platform |
| User settings | `prefers-color-scheme`, `prefers-contrast`, `forced-colors`, `prefers-reduced-motion`, `prefers-reduced-transparency` | The accessibility settings of the platform |
| Language | The `lang` attribute, and `Intl` | The locale API of the platform |

On the web, use the touch target size when `any-pointer: coarse` matches.

## Browsers

1. Write the supported browsers in `docs/conventions/design.md`, under Targets.\
   By default, use only features with the Baseline status "widely available" for the functions of the product.
2. Use a newer feature only as a progressive enhancement, with a fallback that keeps the function.\
   For example, view transitions, scroll-driven animations, and `prefers-reduced-transparency`.
3. Test in each browser engine of the supported browsers.

## Semantics

1. On the web, use the HTML element for each role first.\
   Use WAI-ARIA only when no HTML element does the work, by the WAI-ARIA Authoring Practices Guide.
2. Give each page a unique `title`, one `h1`, and landmarks: `header`, `nav`, `main`, and `footer`.
3. Use `a` to go to a place, and `button` to do an action.
4. Show the focus indicator with `:focus-visible`.
5. Do not stop zoom in the viewport settings.
6. Use logical properties, for example `margin-inline-start`, so that the layout mirrors for right-to-left languages.
7. On a native platform, give each control its role, name, state, and value with the accessibility API:\
   the accessibility modifiers in SwiftUI, semantics in Compose, UI Automation on Windows, and the accessible properties of GTK.

## Motion

1. Use the springs of the platform:\
   `.smooth`, `.snappy`, `.bouncy`, and `Spring(duration:bounce:)` in SwiftUI,\
   `spring()` and `MotionScheme` (standard, or expressive as an experimental API) in Compose,\
   `SpringSimulation` in Flutter, `AdwSpringAnimation` in libadwaita, and the spring animations of the Windows composition API.\
   On the web, use a CSS `linear()` easing that approximates the spring.
2. Animate transform and opacity.\
   On the web, do not animate width, height, position, or margin.\
   The browser must lay out the page again for each frame of them.
3. Keep each frame in the time of one refresh of the display, also at 120 Hz.\
   Test the motion on a slow device.
4. Play vector animations from small files, for example Lottie or Rive files.\
   When reduced motion is on, show the still image.
5. Use a blur (`backdrop-filter` on the web) only with an opaque fallback.

This table gives the names of the APIs for the transitions in the glossary of the `design-conventions` skill.\
A dash means that the platform has no API with that name.\
Then make the pattern with the general animation API of the platform.

| Pattern | SwiftUI | Jetpack Compose | Flutter | Web | WinUI |
| --- | --- | --- | --- | --- | --- |
| Shared element transition | `matchedGeometryEffect`, `navigationTransition(.zoom)` with `matchedTransitionSource` | `SharedTransitionLayout` with `Modifier.sharedElement` | `Hero` | View transitions with `view-transition-name` | `ConnectedAnimationService` |
| Container transform | `navigationTransition(.zoom)` | `SharedTransitionLayout` with `Modifier.sharedBounds` | `OpenContainer` (`animations` package) | View transitions | `ConnectedAnimationService` |
| Shared axis | - | `AnimatedContent` | `SharedAxisTransition` (`animations` package) | View transitions | `SlideNavigationTransitionInfo` |
| Fade through | - | `AnimatedContent` | `FadeThroughTransition` (`animations` package) | View transitions | - |
| Fade | `.transition(.opacity)` | `AnimatedVisibility` with `fadeIn` and `fadeOut` | `FadeScaleTransition` (`animations` package) | A CSS transition of `opacity` | - |
| Push | `NavigationStack` | Navigation Compose | `MaterialPageRoute`, `CupertinoPageRoute` | View transitions | `DrillInNavigationTransitionInfo` |
| Scroll-driven animation | `scrollTransition`, `visualEffect` | - | - | `animation-timeline: scroll()` and `view()` | - |

## Text and localization

1. Keep all UI text in resource files with keys.\
   Do not put UI text in the code.
2. Use the message format and the plural rules of the platform, for example ICU MessageFormat.
3. Format dates, times, numbers, currencies, names, and addresses with the locale functions of the platform, for example `Intl` on the web.\
   Do not make these formats by hand.
4. On the web, use `word-break: keep-all` for Korean text.
