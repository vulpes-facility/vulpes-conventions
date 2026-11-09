# Typography

## Fonts

1. Use the fonts of the base design system ([`design-systems.md`](design-systems.md)).\
   When it has none, use the system font of the platform (`SKILL.md`, section 4).
2. Use a brand font only when the product needs it.\
   Before you use it, make sure that its license allows each use: apps, the web, and embedding.
3. Use one font family for the UI.\
   Add a second family only for a clear purpose, for example a monospace font for code.
4. Make sure that the fonts have the glyphs of each script that the product supports.\
   When they do not, select a fallback font for each script, and test it.\
   For example, test Hangul, Japanese, Chinese, Arabic, and Thai.
5. When the product needs many weights or widths of one family, use a variable font.\
   When the font has an optical size axis, let it follow the font size.

## Type scale

1. Make the type scale from roles, not from sizes: display, headline, title, body, label, and caption.\
   Each role is a token with a font, a size, a weight, a line height, and a letter spacing.
2. On a native platform, map each role to a text style of the platform:\
   a. The Dynamic Type text styles on Apple platforms.\
   b. The Material type scale on Android.\
   c. The Fluent type ramp on Windows.\
   d. The libadwaita style classes in GNOME.
3. Show the hierarchy with size and weight.\
   Do not use upper case for long text.\
   Underline only links.
4. On the web, use at least 16 CSS px for long text.

## Text size settings

1. Make text follow the text size setting of the user (`SKILL.md`, section 4).
2. At 200% text size, no text and no function can be lost (WCAG 1.4.4).\
   Let the layout change: wrap, stack, or scroll.\
   Do not truncate text.
3. Do not put text in a container with a fixed height.

## Readability

1. Give body text a line height of about 1.5 times the font size.
2. Keep lines of long text at 80 characters or less, and at 40 characters or less for Chinese, Japanese, and Korean.
3. The layout MUST work when the user changes the text spacing to these values (WCAG 1.4.12):\
   line height 1.5, paragraph spacing 2, letter spacing 0.12, and word spacing 0.16 times the font size.
4. Align text to the start edge.\
   Do not justify text.
5. Use tabular figures for numbers in tables and for numbers that change.\
   Then the columns align, and the digits do not move.
6. Break Korean text between words, not in a word.
