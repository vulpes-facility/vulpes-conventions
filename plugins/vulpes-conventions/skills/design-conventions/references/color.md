# Color

## Roles

Give each color a role.\
Make semantic tokens for these roles at least:

| Role | Use it for |
| --- | --- |
| Background and surface | The window, the page, and the containers on it, for each level of elevation |
| Text and icon | Primary, secondary, and disabled content, and content on a colored background |
| Border | Separators, input borders, and focus indicators |
| Accent | The primary action, the selection, and links |
| Status | Danger, warning, success, and information |

1. Use the accent color only for actions and the selection.\
   When the accent color is in many places, the user cannot find the primary action.
2. Use the status colors only for a status.\
   Do not use the danger color for decoration.

## Contrast

1. Text MUST have a contrast ratio of at least 4.5:1 with its background (WCAG 1.4.3).\
   Large text MUST have at least 3:1.\
   Large text is 24 CSS px and larger, or 18.66 CSS px and larger in bold.
2. These parts MUST have a contrast ratio of at least 3:1 with the colors next to them (WCAG 1.4.11):\
   icons that have a meaning, input borders, focus indicators, and the parts of a control that show its state.
3. Check the contrast in each theme and in each state: hover, pressed, selected, and error.
4. A disabled control does not need a minimum contrast.\
   But the user MUST be able to see that the control is there.
5. Do not put text on an image without an overlay or a background that gives the contrast.

## Meaning

1. Do not show information only with color (WCAG 1.4.1).\
   Also use text, an icon, a pattern, or a shape.\
   For example, show a field with an error with an icon and a message, not only with a red border.
2. Do not make red and green the only difference between two states.\
   Many users cannot see this difference.

## Scales

1. Make each color scale in a perceptual color space, for example OKLCH.\
   Then the same step has about the same lightness in each hue, and gives about the same contrast.
2. Give each scale enough steps for the backgrounds, the borders, and the text of each theme, for example 10 to 12 steps.
3. A color MAY be outside sRGB, for example in Display P3, for displays with a wide gamut.\
   Give each such color an sRGB fallback, and check the contrast with the sRGB value.

## Dark and high-contrast themes

1. Make the dark theme as a separate set of values for the semantic tokens.\
   Do not invert the light theme.
2. In the dark theme, use dark gray surfaces.\
   Show elevation with lighter surfaces, because shadows are difficult to see on a dark background.
3. In the dark theme, use less saturated colors for large areas.\
   Large areas of saturated color are too bright on a dark background.
4. Support the contrast settings of each platform:\
   a. Increase Contrast on Apple platforms.\
   b. High contrast text on Android.\
   c. Contrast themes on Windows.\
   d. High Contrast in GNOME.\
   e. The contrast and forced colors settings on the web.
5. In forced colors, use the system colors.\
   Keep the borders and the focus indicators visible.
