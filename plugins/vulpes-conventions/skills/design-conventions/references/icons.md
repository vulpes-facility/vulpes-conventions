# Icons and images

## Icons

1. Use one icon set in the product: the set of the base design system.\
   When the base design system is a platform guideline, use the icons of the platform:\
   SF Symbols on Apple platforms, Material Symbols on Android, Fluent System Icons on Windows, and the Adwaita symbolic icons in GNOME.
2. Use the sizes of the icon set, for example 16, 20, and 24.\
   Do not scale an icon to a size between them.
3. Give each icon one meaning in the whole product.
4. Put a text label next to an icon, unless the icon is well known and the space is small, for example search or close.
5. Give each button with only an icon an accessible name.\
   On a platform with a pointer, also give it a tooltip.
6. Color icons with the text and icon tokens.\
   An icon that has a meaning MUST have a contrast ratio of at least 3:1 ([`color.md`](color.md)).
7. In a right-to-left language, mirror the icons that show a direction or an order, for example back, forward, and a list with indents.\
   Do not mirror icons of real objects, check marks, media controls, or clocks.

## Images and illustrations

1. Give each image that has information a text alternative.\
   Mark each decorative image as decorative.
2. Do not put text in images, except in logos.\
   Text in an image cannot be translated, made larger, or read by a screen reader.
3. Give each image a fixed aspect ratio, so that the layout does not move when the image loads.
4. Give each raster image a size for each pixel density, or use a vector image.
5. Use one style for all illustrations in the product.

## App icons

1. Make the app icon by the specs of each platform: the shape, the sizes, the safe zone, and the variants.\
   For example, an adaptive icon and a monochrome icon on Android, and the layered icon with its dark and tinted variants on Apple platforms.
2. On the web, give a favicon, an icon for the home screen, and a maskable icon for an installable web app.
3. In GNOME, give a full-color app icon and a symbolic icon.
