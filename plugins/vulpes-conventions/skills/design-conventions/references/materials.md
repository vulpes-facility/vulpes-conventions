# Materials and depth

Materials are the surfaces of the UI: opaque backgrounds, translucent and blurred surfaces, and the elevation between them.\
[`glossary.md`](glossary.md) gives the names of the materials of each platform.

## Layers

1. Keep two layers: the content layer, and the functional layer above it.\
   The functional layer contains the navigation, the toolbars, and the controls.
2. Use translucent or blurred materials only in the functional layer and on temporary surfaces, for example menus, popovers, and sheets.\
   Use opaque materials for the content.
3. Use the materials of the platform:

   | Platform | Functional layer and temporary surfaces | Window and content |
   | --- | --- | --- |
   | Apple platforms | Liquid Glass, from the system components | The standard materials |
   | Windows | Acrylic | Mica |
   | Android | Material 3 surfaces with tonal elevation | Material 3 surface colors |
   | GNOME | Opaque libadwaita surfaces | Opaque libadwaita surfaces |
   | Web | The materials of the base design system | Opaque surfaces |

4. On Apple platforms, get Liquid Glass from the system components.\
   Use it only for the most important controls and the navigation.\
   Do not put it in the content layer.\
   Some system controls in the content layer, for example sliders and toggles, use it while the user moves them.\
   Do not give bars and controls custom backgrounds, because they interfere with the system material.
5. Give each translucent surface an opaque fallback for a platform or a browser that cannot show it.

## Contrast and settings

1. Text and icons on a translucent material MUST keep the contrast of [`color.md`](color.md) on each content that can be under them.\
   Test with light, dark, and busy content under the material.
2. Follow the reduced transparency setting of each platform:\
   Reduce Transparency on Apple platforms and Transparency effects on Windows, also in web apps where the browser gives the setting.\
   With this setting, use opaque surfaces.\
   The system materials follow these settings.\
   A custom material MUST follow them too.
3. In forced colors and high-contrast settings, use opaque system colors.

## Elevation

1. Show elevation with the method of the base design system: shadows, tonal surface colors, or lighter surfaces in the dark theme ([`color.md`](color.md)).
2. Use a small number of elevation levels, and give each level a token.\
   Give the same kind of surface the same level on each screen.
3. Put a scrim under a modal surface, to show that the content under it is not available.

## Performance

1. A blur uses much GPU time.\
   Keep blurred areas small.\
   Do not put a blurred surface on a different blurred surface.
