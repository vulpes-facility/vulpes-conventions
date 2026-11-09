# Glossary

This file gives the names of design patterns, and their other names on each platform.\
The rules for the patterns are in the other reference files.

1. When you write about a design, use the name in the first column.
2. When the user uses a name from the second column, use the pattern of that row.
3. Some names have more than one meaning (see Names with more than one meaning).\
   Use the meaning that fits the platform and the context.\
   When the meaning is not clear, ask the user.

## Transitions and motion

Rules: [`motion.md`](motion.md).

| Name | Other names | What it is | Use it for |
| --- | --- | --- | --- |
| Shared element transition | Hero animation (Flutter), matched geometry (SwiftUI), zoom transition (iOS), connected animation (Windows) | One element moves and changes its size from its place on the first screen to its place on the second screen | The detail of an item that the user selected, for example a photo |
| Container transform | Open container (Flutter) | A container, for example a card, a list item, or a button, grows into the next screen or surface | A card or a list item that opens its detail, and a button that opens a sheet |
| Shared axis | Forward and backward, lateral (Material) | The old screen and the new screen move together on one axis: X, Y, or Z | Steps in a flow, and levels in a hierarchy |
| Fade through | Top level (Material) | The old screen fades out, then the new screen fades in and grows a little | Top-level destinations with no relation, for example tabs |
| Fade | Enter and exit (Material), crossfade, dissolve | An element fades in or out, sometimes with a small change of scale | Dialogs, menus, snackbars, and content that changes in place |
| Push | Slide, drill-in (Windows) | The new screen comes in from the trailing edge, and back moves it out | Navigation in a navigation stack |
| Modal presentation | Sheet presentation, cover | A surface comes up from the bottom or over the screen, with a scrim | A task that the user starts and ends in one place |
| Predictive back | Back preview | During the back gesture, the current screen becomes smaller and shows the screen under it | Back on Android |
| Morph | Shape morphing | A shape changes into a different shape | The state change of a control, and the loading indicator of Material 3 Expressive |
| Stagger | Cascade | Elements start one after the other, with a short delay | Lists and grids that appear |
| Choreography | Motion sequence | The order and timing of all elements in one transition | Transitions with more than one moving element |
| Micro-interaction | | A small animation on one control, in response to an input | Toggles, like buttons, and a copy confirmation |
| Parallax | | Layers move at different speeds when the user scrolls | A hero section or a header, in a small amount |
| Scroll-driven animation | Scroll-linked animation, scroll-triggered animation | An animation whose progress follows the scroll position, or that starts at a scroll position | A collapsing header, a reading progress bar, and content that appears |
| Collapsing header | Large title (iOS), large top app bar (Material) | A large header that becomes a small bar when the user scrolls | The first screen of a section |
| Overscroll | Rubber banding (iOS), stretch overscroll (Android) | The content moves or stretches past its edge, and then comes back | The end of a scrolled area (the system gives it) |
| Ripple | Ink ripple, state layer (Material) | A press effect that spreads from the touch point | Press feedback on Material components |
| Spring | Physics-based animation | Motion that physics calculates from a duration and a bounce, or from a stiffness and a damping | Movement, changes of size and shape, and gestures |
| Bounce | Overshoot | A spring goes past its end value, and then comes back | Expressive motion, and the end of a thrown element |
| Easing | Easing curve, timing function | The change of speed in a motion with a fixed duration | Fades and color changes |
| Velocity handoff | | A spring starts with the speed of the gesture at the release | Elements that the user drags or throws |
| Vector animation | Lottie or Rive animation | An animation in a vector file that the app plays | Illustrations in empty states, onboarding, and celebrations |
| Haptic feedback | Haptics | A short vibration pattern of the system | Success, failure, a snap to a position, and a limit |

## Navigation and layout

Rules: [`layout.md`](layout.md), [`platforms.md`](platforms.md).

| Name | Other names | What it is | Use it for |
| --- | --- | --- | --- |
| Navigation bar | Tab bar (iOS), bottom navigation | A bar at the bottom with 3 to 5 top-level destinations | Compact windows |
| Navigation rail | | A narrow bar of destinations at the side | Medium and expanded windows |
| Sidebar | Navigation drawer (Material), navigation view (Windows), source list (macOS) | A side panel with destinations and groups | Expanded and larger windows, and desktop apps |
| Top app bar | Navigation bar (iOS), header bar (GNOME), title bar | A bar at the top with the title, back, and actions | Each screen |
| List-detail | Master-detail, split view, navigation split view (SwiftUI) | A list, and the detail of the selected item, side by side or one at a time | Mail, settings, and files |
| Supporting pane | Inspector (Apple) | A second pane next to the main content | Properties, comments, and filters |
| Feed | | A long scrolled list of items of the same kind | Posts, news, and activity |
| Card grid | Gallery | A grid of cards of the same size | Products, photos, and projects |
| Bento grid | Bento layout | A grid of cards of different sizes | An overview, or a landing page with a few highlights |
| Masonry | Waterfall layout | Columns of items with different heights, with no rows | Photos and saved items |
| Hero section | Hero banner, hero header | A large area at the top of a page with the main message and action | Landing pages |
| Carousel | Slider | A row of items that scrolls to the side | A small set of items to browse. Material 3 has the multi-browse, uncontained, and hero layouts |
| Bottom sheet | Sheet (iOS), modal or standard bottom sheet (Material) | A surface that comes up from the bottom | Secondary content and short tasks in compact windows |
| Side sheet | | A surface at the side of the window | Secondary content in larger windows |
| Dialog | Alert, content dialog (Windows) | A small window that stops the work until the user decides | Decisions that must come first ([`components.md`](components.md)) |
| Popover | Flyout (Windows), popup | A small surface next to the control that opened it | Short options and details in larger windows |
| Full-screen cover | Full-screen modal | A modal screen that covers all of the window | Tasks that need the full screen, for example a camera |
| Command palette | Command menu, ⌘K menu | A search field that finds and runs commands | Desktop and web apps with many commands |
| Context menu | Right-click menu, long-press menu | A menu of actions for one item | Actions on an item |
| Overflow menu | More menu, kebab menu, meatball menu | A menu behind a "more" button | Actions that do not fit in a bar |
| Floating action button | FAB, extended FAB | A button above the content for the primary action (Material) | The one primary action of a screen on Android |
| Segmented control | Segmented button (Material), toggle group | A row of connected buttons with one selected | A change between 2 to 5 views or options |
| Chip | Tag, pill, token | A small element for a filter, a choice, an input, or a suggestion | Filters and selected values |

## Feedback and states

Rules: [`components.md`](components.md).

| Name | Other names | What it is | Use it for |
| --- | --- | --- | --- |
| Snackbar | Toast | A short message at the bottom or the top that goes away | A short status that needs no action |
| Banner | Info bar (Windows), message bar | A message across the top of the content that stays until the user acts | An important status for the full screen |
| Inline message | Inline alert, callout | A message next to the content that it is about | Errors of a field, and warnings in a section |
| Badge | Count, dot | A small mark with a count or a status on an element | New items and unread counts |
| Tooltip | | A short label that shows on hover or focus | The names of icon buttons on desktop and the web |
| Empty state | Zero state, blank slate | A view with no content, with the reason and an action | First use, no results, and a cleared list |
| Skeleton | Skeleton screen, shimmer, placeholder | Gray shapes of the layout that comes | A wait when the layout is known |
| Spinner | Activity indicator (iOS), indeterminate circular progress indicator, progress ring (Windows) | A shape that turns while the app works | A short wait with no known length |
| Progress bar | Linear progress indicator, progress view | A bar that fills to show the progress | A wait with a known length |
| Loading indicator | | A shape that morphs in a loop (Material 3 Expressive) | A short wait in Material 3 Expressive |
| Optimistic update | Optimistic UI | The UI shows the result before the server confirms it, and goes back when it fails | Fast actions with a low risk of failure, for example a like |
| Pull to refresh | Swipe to refresh, refresh control | The user pulls the top of a list down to load new items | Feeds and lists that the user updates |
| Infinite scroll | Endless scroll | More items load when the user comes near the end | Feeds |
| Pagination | Paging | Pages with numbers, or next and previous controls | Search results and tables, and lists where the user must find a position again |

## Interaction

| Name | Other names | What it is | Use it for |
| --- | --- | --- | --- |
| Swipe actions | Swipe to delete, leading and trailing swipe actions | Actions that show when the user swipes a list item | Actions on list items with touch. Also give them in a menu ([`input.md`](input.md)) |
| Drag and drop | | The user moves an item with a pointer or a finger | Reordering and moving items. Also give a control for it ([`input.md`](input.md)) |
| Long press | Press and hold | The user holds a finger on an element | Context menus with touch |
| Progressive disclosure | | Advanced options show only when the user asks for them | Complex forms and settings |
| Inline editing | Edit in place | The user changes a value where it shows | Titles, and cells of tables |

## Surfaces and depth

Rules: [`materials.md`](materials.md).

| Name | Other names | What it is | Use it for |
| --- | --- | --- | --- |
| Elevation | Z-depth | The distance of a surface above the background, shown with a shadow or a color | The order of surfaces |
| Tonal elevation | Surface containers (Material 3) | Elevation shown with the tone of the surface color | Material 3 |
| Scrim | Overlay, backdrop, dimming layer | A dark translucent layer under a modal surface | Dialogs, sheets, and drawers |
| Liquid Glass | | The translucent material of Apple platforms that bends the light of the content under it | Controls and navigation on Apple platforms |
| Mica | | An opaque Windows material with a tint from the desktop background | Window backgrounds on Windows |
| Acrylic | | A translucent, blurred Windows material | Flyouts and menus on Windows |
| Vibrancy | | Text and icons on an Apple material that take color from the content under it | Labels on materials on Apple platforms |
| Glassmorphism | Frosted glass, backdrop blur | A web style of translucent, blurred surfaces | Only by the rules of [`materials.md`](materials.md) |

## Foundations

| Name | Other names | What it is | Rules |
| --- | --- | --- | --- |
| Design token | Token | A named value of the design system | [`tokens.md`](tokens.md) |
| Semantic color | Color role | A color token named by its role | [`color.md`](color.md) |
| Dynamic color | Material You | Colors that the system makes from the wallpaper (Android) | [`platforms.md`](platforms.md) |
| Wide gamut | Display P3 | Colors outside sRGB that newer displays can show | [`color.md`](color.md) |
| Type scale | Type ramp (Windows), text styles (Apple) | The set of text roles and their sizes | [`typography.md`](typography.md) |
| Variable font | | One font file with axes, for example weight, width, and optical size | [`typography.md`](typography.md) |
| Tabular figures | Monospaced numerals | Digits that all have the same width | [`typography.md`](typography.md) |
| Spacing scale | Space scale | The set of space steps | [`tokens.md`](tokens.md) |
| Inset, stack, and inline space | Padding, gap | The space in a container, between elements above and below, and between elements side by side | [`tokens.md`](tokens.md) |
| Density | Compact, comfortable | The amount of space and size in the UI | [`tokens.md`](tokens.md) |
| Concentric corners | Nested radius | Corners of nested shapes with the same center | [`tokens.md`](tokens.md) |
| Margin | Page margin | The space between the edge of the window and the content | [`layout.md`](layout.md) |
| Gutter | Column gap | The space between the columns of a grid | [`layout.md`](layout.md) |
| Safe area | Insets | The part of the screen that the system does not cover | [`layout.md`](layout.md) |
| Window size class | Breakpoint | A range of window widths with one layout | [`layout.md`](layout.md) |
| Container query | | A style rule that uses the size of the container, not of the window | [`layout.md`](layout.md) |

## Names with more than one meaning

| Name | Meanings |
| --- | --- |
| Hero | 1. A shared element transition (the `Hero` widget of Flutter). 2. A large area at the top of a web page (hero section). 3. A carousel layout with one large item (Material 3). |
| Navigation bar | 1. The bottom bar of top-level destinations (Material). 2. The top bar with the title and back (iOS). |
| Toast | 1. A short message in the app (web design systems). 2. A system notification outside the app (Windows). |
| Banner | 1. A message across the top of the content (Material, web). 2. A system notification at the top of the screen (iOS). |
| Sheet | 1. A modal surface from the bottom (iOS, Material). 2. A modal surface attached to the top of a window (macOS). |
| Drawer | 1. A navigation panel at the side (Material). 2. A panel that comes in from an edge of the window (web). |
