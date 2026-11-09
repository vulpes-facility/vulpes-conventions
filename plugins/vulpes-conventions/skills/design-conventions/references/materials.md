# Materials and depth

## Layers

1. Keep two layers: the content layer, and above it the functional layer with the navigation and the controls.
2. Use translucent or blurred materials only in the functional layer and on temporary surfaces, for example menus and sheets.\
   Use opaque materials for the content.
3. Use the materials of the platform:

   | Platform | Functional layer and temporary surfaces | Window and content |
   | --- | --- | --- |
   | Apple platforms | Liquid Glass, from the system components | The standard materials |
   | Windows | Acrylic | Mica |
   | Android | Material 3 surfaces with tonal elevation | Material 3 surface colors |
   | GNOME | Opaque libadwaita surfaces | Opaque libadwaita surfaces |
   | Web | The materials of the base design system | Opaque surfaces |

4. On Apple platforms, use Liquid Glass only for the most important controls and the navigation, not in the content layer.\
   Do not give bars and controls custom backgrounds, because they interfere with the system material.
5. Give each translucent surface an opaque fallback for a platform or a browser that cannot show it.
6. Keep blurred areas small, and do not put a blurred surface on a different blurred surface.

## Contrast and settings

1. Text and icons on a translucent material MUST keep the WCAG contrast (1.4.3, 1.4.11) on each content that can be under them.
2. Follow the reduced transparency setting of each platform, also in web apps where the browser gives it.\
   Examples are Reduce Transparency on Apple platforms and Transparency effects on Windows.\
   With this setting, use opaque surfaces.
3. In forced colors and high-contrast settings, use opaque system colors.

## Elevation

1. Show elevation with the method of the base design system: shadows, tonal surface colors, or lighter surfaces in the dark theme.
2. Use a small number of elevation levels, each with a token.
3. Put a scrim under a modal surface.
