# Layout

## Window sizes

1. Design for the width of the window, not for the name of a device.\
   A phone in landscape, a tablet in split view, and a small desktop window can have the same width.
2. Use the window size classes of the base design system.\
   When it has none, use these classes from Material 3.\
   The widths are in dp, or in CSS px on the web.

   | Class | Width | Main navigation | Panes |
   | --- | --- | --- | --- |
   | Compact | Less than 600 | Navigation bar at the bottom | 1 |
   | Medium | 600 to 839 | Navigation rail | 1 |
   | Expanded | 840 to 1199 | Navigation rail or sidebar | 1 or 2 |
   | Large | 1200 to 1599 | Sidebar | 1 or 2 |
   | Extra large | 1600 or more | Sidebar | 1 to 3 |

3. Design the compact class first.\
   Then add the changes for each larger class.
4. The content MUST work at a width of 320 CSS px with no horizontal scroll (WCAG 1.4.10).\
   Content that needs two dimensions, for example a table, a map, or a diagram, MAY scroll in its own area.
5. Support both orientations, unless a function needs one (WCAG 1.3.4).
6. Give a desktop window a minimum size.\
   Make the layout work at each size from the minimum size to full screen.\
   Keep the size and the position of the window when the app closes, and use them again when it opens.
7. Make a component adapt to the size of its container, not only to the size of the window.\
   Then it works in a sidebar and in the main area.

## Grid and space

1. Put each element on the grid of the space scale ([`tokens.md`](tokens.md)).
2. Use the column grid of the base design system.\
   When it has none, use 4 columns for compact, 8 columns for medium, and 12 columns for expanded and larger.
3. Show groups with space.\
   Make the space larger at each level: in a component, between related elements, between groups, and between sections.
4. Align elements on shared edges.
5. Limit the width of long text ([`typography.md`](typography.md)).

## Safe areas and system bars

1. Keep content and controls out of the system areas:\
   the camera cutout, the status bar, the home indicator, the navigation bar, and the round corners of the screen.\
   Let the backgrounds go under the system bars.
2. On Android, design edge to edge.
3. Keep controls away from the screen edges where the system gestures start.

## Order and direction

1. Make the visual order, the reading order, and the focus order the same.
2. For a right-to-left language, mirror the layout.\
   Mirror the navigation, the alignment, the order of elements, and the icons that show a direction ([`icons.md`](icons.md)).\
   Do not mirror numbers, logos, media controls, or text in a left-to-right script.
3. Write "start" and "end", not "left" and "right", in the specs.
