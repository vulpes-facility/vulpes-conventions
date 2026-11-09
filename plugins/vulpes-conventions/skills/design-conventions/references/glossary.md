# Glossary

This file gives the names of design patterns, and their other names on each platform.

1. When you write about a design, use the name in the first column.
2. When the user uses a name from the second column, use the pattern of that row.
3. Some names have more than one meaning (see the last section).\
   Use the meaning that fits the platform and the context.\
   When the meaning is not clear, ask the user.

## Transitions and motion

| Name | Other names |
| --- | --- |
| Shared element transition | Hero animation (Flutter), matched geometry (SwiftUI), zoom transition (iOS), connected animation (Windows) |
| Container transform | Open container (Flutter) |
| Shared axis | Forward and backward, lateral (Material) |
| Fade through | Top level (Material) |
| Fade | Enter and exit (Material), crossfade, dissolve |
| Push | Slide, drill-in (Windows) |
| Predictive back | Back preview (Android) |
| Scroll-driven animation | Scroll-linked animation, scroll-triggered animation |
| Collapsing header | Large title (iOS), large top app bar (Material) |
| Overscroll | Rubber banding (iOS), stretch overscroll (Android) |
| Ripple | Ink ripple, state layer (Material) |

## Navigation and layout

| Name | Other names |
| --- | --- |
| Navigation bar | Tab bar (iOS), bottom navigation |
| Sidebar | Navigation drawer (Material), navigation view (Windows), source list (macOS) |
| Top app bar | Navigation bar (iOS), header bar (GNOME), title bar |
| List-detail | Master-detail, split view, navigation split view (SwiftUI) |
| Supporting pane | Inspector (Apple) |
| Bottom sheet | Sheet (iOS), modal or standard bottom sheet (Material) |
| Dialog | Alert, content dialog (Windows) |
| Popover | Flyout (Windows), popup |
| Overflow menu | More menu, kebab menu, meatball menu |
| Segmented control | Segmented button (Material), toggle group |

## Feedback and surfaces

| Name | Other names |
| --- | --- |
| Snackbar | Toast |
| Banner | Info bar (Windows), message bar |
| Spinner | Activity indicator (iOS), indeterminate circular progress indicator, progress ring (Windows) |
| Progress bar | Linear progress indicator, progress view |
| Tonal elevation | Surface containers (Material 3) |

## Names with more than one meaning

| Name | Meanings |
| --- | --- |
| Hero | 1. A shared element transition (the `Hero` widget of Flutter). 2. A large area at the top of a web page (hero section). 3. A carousel layout with one large item (Material 3). |
| Navigation bar | 1. The bottom bar of top-level destinations (Material). 2. The top bar with the title and back (iOS). |
| Toast | 1. A short message in the app (web design systems). 2. A system notification outside the app (Windows). |
| Banner | 1. A message across the top of the content (Material, web). 2. A system notification at the top of the screen (iOS). |
| Sheet | 1. A modal surface from the bottom (iOS, Material). 2. A modal surface attached to the top of a window (macOS). |
| Drawer | 1. A navigation panel at the side (Material). 2. A panel that comes in from an edge of the window (web). |
