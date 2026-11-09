# Motion

[`glossary.md`](glossary.md) gives the names of the motion patterns and their names on each platform.

## Purpose

1. Use motion to show a cause and its result, a change of state, where an element comes from and goes to, or a wait.
2. Do not use motion only for decoration.
3. Do not let motion stop input.\
   The user can act while an animation runs.

## Springs

1. Use springs for motion that moves an element, changes its size or shape, or follows a gesture.\
   A spring starts from the current position and speed.\
   Thus the motion stays smooth when the user stops it or changes its direction.
2. Use the springs of the base design system or of the platform.\
   For example, Material 3 has spatial springs for position, size, and shape, and effects springs for color and opacity.
3. Give each spring as a token ([`tokens.md`](tokens.md)).\
   Use the form of the platform: a duration and a bounce, or a stiffness and a damping ratio.
4. Use bounce only where the product wants an expressive feel.\
   Do not use bounce for color or opacity.
5. When the user releases a dragged or thrown element, start the spring with the speed of the gesture.

## Duration and easing

1. Use a fixed duration with an easing curve for a change that does not move, for example a fade or a color change.\
   Also use it when the platform or the tool has no springs.
2. Use the duration and easing tokens of the base design system.\
   When it has none, use these durations:

   | Change | Duration |
   | --- | --- |
   | Small: a state, a toggle, or an icon | 100 to 150 ms |
   | Medium: a menu, a dialog, or a panel that expands | 200 to 300 ms |
   | Large: a transition of the full screen | 300 to 500 ms |

3. Make an exit faster than an entrance.
4. Use these easing curves:\
   a. Ease-out for an element that comes in.\
   b. Ease-in for an element that goes out.\
   c. Ease-in-out for an element that moves on the screen.

## Transitions

1. Select the transition by the relation between the two screens:

   | Relation | Transition |
   | --- | --- |
   | The element that the user selected becomes the next screen | Container transform, or shared element transition |
   | The screens are steps in a flow, or levels in a hierarchy | Shared axis, or push |
   | The screens are top-level destinations with no relation | Fade through |
   | A surface comes over the screen | Fade, or the modal presentation of the platform |

2. For navigation between screens, use the system transitions of the platform: push on iOS, predictive back on Android, and the page transitions of Windows.
3. Make the back transition the reverse of the forward transition.
4. A function MUST NOT need a transition.\
   It MUST work also when the platform or the browser cannot show the transition.

## Choreography

1. When more than one element moves, move first the element that the user acted on.\
   Then move the related elements.
2. Stagger the items of a list with a short delay.\
   Animate only the items that are on the screen.
3. Let a transition that a gesture controls follow the finger.\
   The user can reverse it before the release.
4. Keep scroll-linked motion, for example a collapsing header or parallax, in step with the scroll.

## Performance

1. Keep motion smooth on the slowest target device, also on displays with 120 Hz.

## Reduced motion

1. Follow the reduced motion setting of each platform:\
   Reduce Motion on Apple platforms, Remove animations on Android, Animation effects on Windows, and the animation setting of GNOME.\
   Web apps follow the same settings.
2. With reduced motion, replace movement, zoom, parallax, and bounce with a fade, or with no animation.\
   Keep the information that the motion gave.\
   Show a still image in place of an illustration that moves.\
   Progress indicators can continue.
3. Do not show content that flashes more than 3 times in one second (WCAG 2.3.1).
4. Give a pause control for motion that starts by itself and lasts more than 5 seconds (WCAG 2.2.2).\
   Do not start a video with sound by itself.
