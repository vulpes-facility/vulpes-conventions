# Motion

1. Do not let motion stop input.\
   The user can act while an animation runs.

## Springs

1. Use springs for motion that moves an element, changes its size or shape, or follows a gesture.\
   A spring keeps the motion smooth when the user stops it or changes its direction.
2. Use the springs of the base design system or of the platform.\
   For example, Material 3 has spatial springs for position, size, and shape, and effects springs for color and opacity.
3. Give each spring as a token ([`tokens.md`](tokens.md)): a duration and a bounce, or a stiffness and a damping ratio.
4. Use bounce only where the product wants an expressive feel.\
   Do not use bounce for color or opacity.
5. When the user releases a dragged element, start the spring with the speed of the gesture.

## Duration and easing

1. Use a fixed duration with an easing curve for a change that does not move, for example a fade.\
   Use the tokens of the base design system, or these durations:

   | Change | Duration |
   | --- | --- |
   | Small: a state, a toggle, or an icon | 100 to 150 ms |
   | Medium: a menu, a dialog, or a panel that expands | 200 to 300 ms |
   | Large: a transition of the full screen | 300 to 500 ms |

2. Make an exit faster than an entrance.

## Transitions

1. Select the transition by the relation between the two screens:

   | Relation | Transition |
   | --- | --- |
   | The element that the user selected becomes the next screen | Container transform, or shared element transition |
   | The screens are steps in a flow, or levels in a hierarchy | Shared axis, or push |
   | The screens are top-level destinations with no relation | Fade through |
   | A surface comes over the screen | Fade, or the modal presentation of the platform |

2. For navigation between screens, use the system transitions of the platform.
3. Make the back transition the reverse of the forward transition.

## Performance and reduced motion

1. Keep motion smooth on the slowest target device, also on displays with 120 Hz.
2. Follow the reduced motion setting of each platform:\
   Reduce Motion on Apple platforms, Remove animations on Android, Animation effects on Windows, and the animation setting of GNOME.\
   Web apps follow the same settings.
3. With reduced motion, replace movement, zoom, parallax, and bounce with a fade, or with no animation.\
   Show a still image in place of an illustration that moves.
