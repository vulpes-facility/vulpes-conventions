# Tokens

Design tokens are the named values of a design system: colors, fonts, type sizes, spaces, sizes, radii, shapes, borders, elevation, opacity, materials, and motion.\
This file does not select a token file format or a token tool.

## Tiers

| Tier | Contains | Example names | Used by |
| --- | --- | --- | --- |
| Primitive | The raw values of the palettes and the scales | `color.blue.600`, `space.4` | Semantic tokens only |
| Semantic | The role of a value in the UI | `color.text.primary`, `color.background.danger`, `space.inset.medium` | Screens and components |
| Component | A value for one part of one component | `button.primary.background.hover` | That component only |

1. Screens and components MUST use semantic or component tokens.\
   Do not use a primitive token in a screen or a component, because a theme changes only the semantic tier.
2. Give each semantic token a primitive token or a different semantic token as its value.\
   Do not give a semantic token a raw value.
3. Add a component token only when the component needs a value that no semantic token gives.
4. When the project has a base design system, use its tokens and its names ([`design-systems.md`](design-systems.md)).\
   Add a token only for a role that the base design system does not have.

## Names

1. Name a token in this order: category, role, variant, state.\
   For example, `color.border.input.focus`.
2. Name a semantic token by its role, not by its value.\
   Write `color.text.danger`, not `color.text.red`.
3. Use the same words in the design files and in the code.\
   Only the form of the name can change for each platform.
4. Do not change the meaning of a token.\
   To change a role, add a new token, mark the old token as deprecated, and remove it in a later major version.

## Scales

1. Make each scale from a small set of steps.\
   Use only those steps.
2. Make the space and size scale on a 4-unit grid, for example 2, 4, 8, 12, 16, 24, 32, 48, and 64.\
   When the base design system has a scale, use it.
3. Write sizes in units that do not change with the pixel density of the screen:\
   CSS px on the web, pt on Apple platforms, dp on Android, epx on Windows, and logical px in GTK.
4. Give each space token one of these roles:\
   a. Inset: the space in a container.\
   b. Stack: the space between elements above and below.\
   c. Inline: the space between elements side by side.
5. When the product needs more than one density, for example compact and comfortable, change the space and size tokens for each density.\
   Do not make a second component for each density.
6. Make a radius scale from none to full, where full makes a pill or a circle.\
   When the base design system has shape tokens, use them.
7. In nested shapes, make the inner radius equal to the outer radius minus the space between the shapes.\
   Then the corners are concentric.
8. Give motion as tokens: springs, and durations with easing curves.\
   [`motion.md`](motion.md) tells when to use each.

## Themes

1. A theme changes only the semantic tier: light, dark, high contrast, and brand themes.\
   Components do not change for a theme.
2. Each semantic color token MUST have a value in each theme that the product supports.
3. Follow the appearance setting of the system by default.\
   The product MAY also let the user select light or dark.

## Source

1. Keep one source of the tokens in the repository.
2. The source in the repository is the reference for the tokens.
3. When the user gives a new version of the design files, apply its token changes to the source in the repository.\
   Tell the user each token that changes.
4. When the design files and the source have different values, and the design files are not a new version, keep the source.\
   Tell the user the differences, so that the design files can be updated.
