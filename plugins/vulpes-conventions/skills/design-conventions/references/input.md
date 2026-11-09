# Input

Design for the input capabilities that the device has, not for the name of the device.\
A tablet can have a keyboard and a trackpad, and a laptop can have a touch screen.

## All inputs

1. Support each input method in `docs/conventions/design.md` ([`design-brief.md`](design-brief.md)).
2. The input can change while the app runs.\
   Do not select one input method at the start.
3. Design for the primary input, and also for each other input that is available.\
   Use the pointer effects of the platform, for example the hover effects on iPad with a trackpad.
4. Do the action when the pointer or the finger goes up, not when it goes down.\
   Then the user can cancel by moving away from the control (WCAG 2.5.2).

## Pointer

1. Use hover only to show more.\
   Do not put information or a function only in a hover state, because touch has no hover.
2. Content that shows on hover or focus MUST stay until the user moves away or closes it.\
   The user MUST be able to close it, and to move the pointer onto it (WCAG 1.4.13).
3. Give each item with actions a context menu that opens with a right-click.\
   Give it the same items as the long-press menu on touch.
4. Show the keyboard shortcuts of the commands in the menus and the tooltips.
5. With only a precise pointer, controls MAY use the compact sizes of the platform.\
   Do not make a target smaller than 24 × 24 CSS px (WCAG 2.5.8).

## Touch

1. Use the touch target size of the platform (`SKILL.md`, section 4).\
   Use it whenever touch is available, also on a device that has a pointer too.
2. Give each gesture a control that does the same action with one tap.\
   This applies to swipes, pinches, gestures with more than one finger, gestures that follow a path, and drags (WCAG 2.5.1, 2.5.7).
3. Open the context menu with a long press.\
   On an icon button, a long press MAY show its tooltip.
4. In compact windows, put frequent actions where the thumb reaches them: in the bottom bar and in the lower part of the screen.
5. Keep controls away from the edges where the system gestures start ([`layout.md`](layout.md)).

## Keyboard

1. Each function MUST work with a keyboard (WCAG 2.1.1).\
   The focus order follows the visual order ([`layout.md`](layout.md)).
2. Use the standard keys:\
   a. Tab and Shift+Tab to move between controls.\
   b. The arrow keys to move in a group, for example a list, a menu, tabs, or a grid.\
   c. Enter or Space to do the action.\
   d. Escape to close.
3. Give shortcuts for frequent commands, with the modifier of the platform ([`platforms.md`](platforms.md)).\
   Do not give a shortcut of the system or of the browser a different function.
4. When a shortcut is one character key, let the user turn it off or change it (WCAG 2.1.4).
5. Show the focus indicator for keyboard focus ([`components.md`](components.md)).

## Pen

1. Use a pen as a precise pointer.\
   Use its pressure and its tilt only in functions for drawing and writing.
2. Use the text fields of the system, so that handwriting input works.

## Assistive input

1. Voice control and switch access use the accessibility API of the platform.\
   Give each control a visible label, and put that label in its accessible name (WCAG 2.5.3).
