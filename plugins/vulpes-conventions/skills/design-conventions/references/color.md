# Color

## Roles

1. Give each color a role: background, surface, text, icon, border, accent, or status.
2. Use the accent color only for actions and the selection.\
   Use the status colors only for a status.

## Contrast

1. Check the contrast in each theme and in each state: hover, pressed, selected, and error.
2. A disabled control needs no minimum contrast, but the user MUST be able to see that it is there.
3. Do not put text on an image without an overlay or a background that gives the contrast.

## Scales

1. Make each color scale in a perceptual color space, for example OKLCH.\
   Then the same step gives about the same contrast in each hue.
2. A color MAY be outside sRGB, for example in Display P3.\
   Give it an sRGB fallback, and check the contrast with the sRGB value.

## Dark and high-contrast themes

1. Make the dark theme as a separate set of values for the semantic tokens.\
   Do not invert the light theme.
2. In the dark theme, use dark gray surfaces, and show elevation with lighter surfaces.\
   Use less saturated colors for large areas.
3. Support the contrast settings of each platform:\
   a. Increase Contrast on Apple platforms.\
   b. High contrast text on Android.\
   c. Contrast themes on Windows.\
   d. High Contrast in GNOME.\
   e. The contrast and forced colors settings on the web.
4. In forced colors, use the system colors, and keep the borders and the focus indicators visible.
