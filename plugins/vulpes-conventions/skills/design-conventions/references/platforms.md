# Platforms

`SKILL.md`, section 4, gives the facts of each platform.\
This file gives the rules that agents often miss.

## Web

1. Keep the behavior of the browser: the back button, links that open in a new tab, text selection, and zoom.

## Mobile

1. On iOS and iPadOS, support all Dynamic Type sizes.\
   At the accessibility sizes, change rows to columns where the text does not fit.
2. On Android, support the system back and the predictive back gesture.\
   Do not put a back button in the bottom bar.
3. Ask for a permission only when the user starts the function that needs it, and tell the reason.

## Desktop

1. On macOS, put each command in the menu bar, with its keyboard shortcut.\
   The app menu contains About, Settings (⌘,), Hide, and Quit (⌘Q).
2. On macOS and in GNOME, apply a change in the settings window immediately.\
   Do not give OK or Apply buttons in it.
3. On Windows, an app can draw its own title bar.\
   Then keep the area to drag the window, and the Snap layouts of the maximize button.
4. In GNOME, use a header bar with a main menu, not a menu bar.\
   Give a Keyboard Shortcuts window that opens with Ctrl+?.
5. On Windows, put an icon in the notification area only when the app runs in the background.\
   GNOME shows no tray icons, so use notifications there.

## Apps on more than one platform

These rules apply to apps that use one code base on more than one platform.

1. Use one base design system for the look ([`design-systems.md`](design-systems.md)).
2. Follow each platform for these items:\
   a. Navigation and back.\
   b. System dialogs: alerts, share, file pickers, and permission requests.\
   c. Menus and keyboard shortcuts.\
   d. Text selection and text input.\
   e. Scroll behavior.\
   f. Window controls, and the order of dialog buttons.
3. Use the differences in this table:

   | Item | macOS | Windows | GNOME | iOS, iPadOS | Android |
   | --- | --- | --- | --- | --- | --- |
   | Shortcut modifier | ⌘ | Ctrl | Ctrl | ⌘, with a keyboard | Ctrl, with a keyboard |
   | Window controls | Top left | Top right | Top right | None | None |
   | App commands | Menu bar | Menu bar or command bar in the window | Main menu in the header bar | Toolbar and context menus | Top app bar and its overflow menu |
   | Settings | Settings window (⌘,) | Settings page | Preferences window | Settings screen, or the Settings app | Settings screen |
   | Affirmative button in a dialog | Last (right) | First (left) | Last (right) | Last (right) | Last (right) |
   | Back | Back button in the toolbar | Back button in the title bar or the navigation view | Back button in the header bar | Back button at the top leading edge, edge swipe | System back |
