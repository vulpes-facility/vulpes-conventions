# Typography

## Fonts

1. Use the fonts of the base design system, or the system font of the platform (`SKILL.md`, section 4).
2. Before you use a brand font, make sure that its license allows each use: apps, the web, and embedding.
3. Make sure that the fonts have the glyphs of each script that the product supports.\
   When they do not, select a fallback font for each script, and test it, for example with Hangul.
4. When the font has an optical size axis, let it follow the font size.

## Type scale

1. Make the type scale from roles, not from sizes: display, headline, title, body, label, and caption.
2. On a native platform, map each role to a text style of the platform:\
   a. The Dynamic Type text styles on Apple platforms.\
   b. The Material type scale on Android.\
   c. The Fluent type ramp on Windows.\
   d. The libadwaita style classes in GNOME.
3. On the web, use at least 16 CSS px for long text.

## Text size and readability

1. Make text follow the text size setting of the user.\
   Let the layout wrap, stack, or scroll, and do not truncate text.
2. Do not put text in a container with a fixed height.
3. Keep lines of long text at 80 characters or less.\
   For Chinese, Japanese, and Korean, keep them at 40 characters or less.
4. Use tabular figures for numbers in tables and for numbers that change.
5. Break Korean text between words, not in a word.
