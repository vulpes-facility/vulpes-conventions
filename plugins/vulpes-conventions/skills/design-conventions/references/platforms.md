# Platforms

`SKILL.md`, section 4, gives the facts of each platform.\
This file gives more rules for each platform.

## Web

1. Give each page a unique title and a clear structure of headings.
2. Use a link to go to a place, and a button to do an action.
3. Keep the behavior of the browser: the back button, links that open in a new tab, text selection, and zoom.\
   Do not stop zoom.
4. Design for the browsers that the project supports.\
   A function MUST work without the newer features of a browser, for example view transitions.\
   Use such a feature only to make the experience better.

## iOS and iPadOS

1. Use a tab bar for the top-level sections, and a navigation stack in each section.\
   The back button is at the top leading edge, and a swipe from the leading edge goes back.\
   On iPad, the tab bar MAY change to a sidebar.
2. Use a sheet for a task that the user starts and ends in one place.
3. Support all Dynamic Type sizes, also the accessibility sizes.\
   At the accessibility sizes, change rows to columns where the text does not fit.
4. On iPad, make the layout work in each window size, and support the keyboard, its shortcuts, and the pointer.
5. Use the system haptics only for important feedback.
6. Ask for a permission only when the user starts the function that needs it.\
   Tell the reason in the purpose text.

## Android

1. Use the top app bar, and the navigation bar or the navigation rail by window size ([`layout.md`](layout.md)).
2. Support the system back and the predictive back gesture.\
   Do not put a back button in the bottom bar.
3. Design edge to edge, and keep content in the insets ([`layout.md`](layout.md)).
4. Support font sizes to 200%.\
   Android 14 and later make large text larger with nonlinear scaling.
5. The product MAY use dynamic color when the brand does not need a fixed color.
6. Support large screens, foldables, and free windows with the window size classes.
7. Ask for a permission only when the user starts the function that needs it.

## macOS

1. Put each command in the menu bar, with its keyboard shortcut.\
   Give the standard menus: the app menu, File, Edit, View, Window, and Help.\
   The app menu contains About, Settings (⌘,), Hide, and Quit (⌘Q).
2. Use the standard shortcuts, for example ⌘N, ⌘O, ⌘S, ⌘W, ⌘Z, and ⇧⌘Z.
3. Use a toolbar and a sidebar.\
   The window controls are at the top left.
4. Apply a change in the Settings window immediately.\
   Do not give OK or Apply buttons in it.
5. Give context menus and drag and drop.

## Windows

1. Use the navigation view (left or top) and the command bar.
2. The window controls are at the top right.\
   When the app draws its own title bar, keep the area to drag the window and the Snap layouts of the maximize button.
3. Give keyboard shortcuts with Ctrl, and access keys with Alt.\
   Each control can get the focus with Tab and the arrow keys.
4. Use the Fluent materials, Mica and Acrylic, only as Fluent 2 tells.
5. Put an icon in the notification area only when the app runs in the background.

## Linux (GNOME)

1. Use a header bar with the window title, the main menu at the end, and the window controls.\
   Do not give a menu bar.
2. Make the layout adapt to narrow windows, also for mobile Linux.
3. Apply a change in the Preferences window immediately.
4. Give a Keyboard Shortcuts window that opens with Ctrl+?.
5. Do not use a tray icon, because GNOME does not show one.\
   Use notifications.
6. Follow the accent color and the dark style of the system.

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
