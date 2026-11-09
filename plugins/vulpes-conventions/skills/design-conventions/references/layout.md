# Layout

## Window sizes

1. Design for the width of the window, not for the name of a device.
2. Use the window size classes of the base design system.\
   When it has none, use these classes from Material 3, in dp or in CSS px:

   | Class | Width | Main navigation | Panes |
   | --- | --- | --- | --- |
   | Compact | Less than 600 | Navigation bar at the bottom | 1 |
   | Medium | 600 to 839 | Navigation rail | 1 |
   | Expanded | 840 to 1199 | Navigation rail or sidebar | 1 or 2 |
   | Large | 1200 to 1599 | Sidebar | 1 or 2 |
   | Extra large | 1600 or more | Sidebar | 1 to 3 |

3. Design the compact class first, then add the changes for each larger class.
4. Make a component adapt to the size of its container, so that it works in a sidebar and in the main area.
5. Give a desktop window a minimum size, and make the layout work at each size up to full screen.\
   Keep the size and the position of the window, and use them again at the next start.

## Space

1. Put each element on the grid of the space scale ([`tokens.md`](tokens.md)).
2. Use the column grid of the base design system.\
   When it has none, use 4 columns for compact, 8 for medium, and 12 for expanded and larger.
3. Make the space larger at each level: in a component, between related elements, between groups, and between sections.

## System areas and direction

1. Keep content and controls out of the system areas, for example the camera cutout and the home indicator.\
   Let the backgrounds go under the system bars, also on Android, where apps are edge to edge.
2. Keep controls away from the screen edges where the system gestures start.
3. For a right-to-left language, mirror the layout and the icons that show a direction ([`icons.md`](icons.md)).\
   Do not mirror numbers, logos, media controls, or text in a left-to-right script.
4. Write "start" and "end", not "left" and "right", in the specs.
