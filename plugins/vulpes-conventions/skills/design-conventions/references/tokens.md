# Tokens

Design tokens are the named values of a design system.\
This file does not select a token file format or a token tool.

## Tiers

| Tier | Contains | Example names | Used by |
| --- | --- | --- | --- |
| Primitive | The raw values of the palettes and the scales | `color.blue.600`, `space.4` | Semantic tokens only |
| Semantic | The role of a value in the UI | `color.text.primary`, `color.background.danger`, `space.inset.medium` | Screens and components |
| Component | A value for one part of one component | `button.primary.background.hover` | That component only |

1. Screens and components MUST use semantic or component tokens, not primitive tokens.\
   A theme changes only the semantic tier.
2. Give each semantic token a primitive token or a different semantic token as its value.
3. Add a component token only when no semantic token gives the value.
4. When the project has a base design system, use its tokens and its names.

## Names

1. Name a token in this order: category, role, variant, state, for example `color.border.input.focus`.
2. Name a semantic token by its role, not by its value: `color.text.danger`, not `color.text.red`.
3. Use the same words in the design files and in the code.
4. To change the meaning of a token, add a new token, and mark the old token as deprecated.

## Scales

1. Make each scale from a small set of steps, and use only those steps.
2. Make the space and size scale on a 4-unit grid, unless the base design system has a scale.
3. Write sizes in units that do not change with the pixel density: CSS px, pt, dp, epx, or logical px.
4. Give each space token one of these roles:\
   a. Inset: the space in a container.\
   b. Stack: the space between elements above and below.\
   c. Inline: the space between elements side by side.
5. For more than one density, change the space and size tokens, not the components.
6. Make a radius scale from none to full.\
   In nested shapes, make the inner radius equal to the outer radius minus the space between them.
7. Give motion as tokens: springs, and durations with easing curves ([`motion.md`](motion.md)).

## Themes

1. A theme (light, dark, high contrast, or brand) changes only the semantic tier.\
   Each semantic color token MUST have a value in each theme.
2. Follow the appearance setting of the system by default.

## Source

1. Keep one source of the tokens in the repository.
2. The source in the repository is the reference for the tokens.
3. When the user gives a new version of the design files, apply its token changes to the source in the repository.\
   Tell the user each token that changes.
4. When the design files and the source have different values, and the design files are not a new version, keep the source.\
   Tell the user the differences, so that the design files can be updated.
