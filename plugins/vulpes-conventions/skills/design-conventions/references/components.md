# Components

## Spec

1. When the base design system has the component, use its spec.
2. For each new component, write a spec with these parts:\
   a. The anatomy: the name of each part.\
   b. The variants and the sizes.\
   c. The states (see States).\
   d. The behavior with a pointer, touch, a keyboard, and a screen reader.\
   e. The content: the length of the labels, and what occurs when the text is longer.\
   f. The tokens that it uses.

## States

| State | Show it with |
| --- | --- |
| Enabled | The default look |
| Hover | A change of the background or the border, only for a pointer |
| Focus | A focus indicator for the keyboard |
| Pressed | A change of the background, the elevation, or the scale |
| Selected or checked | A mark or a shape, not only a color |
| Disabled | Less contrast, and no response to input |
| Loading | A progress indicator in the control, and no second input |
| Error | An icon and a message, not only a color |
| Read-only | The value with no input border, and the value can be selected and copied |

1. Show the focus indicator for keyboard focus.\
   Make it at least 2 CSS px thick, with a contrast ratio of at least 3:1 with the colors next to it.
2. Do not let a sticky header, a footer, or a banner hide the element that has focus (WCAG 2.4.11).
3. Make each control work with each input method, with the target size of that input ([`input.md`](input.md)).

## Actions

1. Give each view one primary action at most.
2. Label each button with a verb that tells the result ([`content.md`](content.md)).
3. For an action that deletes or changes data, give an undo when you can.\
   Ask for a confirmation only when the action cannot be undone.
4. Do not disable the submit button of a form to show that the data is not correct.\
   Let the user submit, then show what to correct.
5. When a control is disabled, tell the reason when you can.
6. Give each action a control, also when a gesture can do it ([`input.md`](input.md)).

## Feedback

1. Show a response to each input in less than 100 ms, for example the pressed state.
2. Show the wait by its length:\
   a. When the layout of the content is known, show a skeleton of it.\
   b. When the length is not known, show an indeterminate progress indicator.\
   c. When the length is known, show a progress bar with the value.
3. Show a snackbar only for a short status that needs no action.\
   Do not make it the only path to an action.\
   Give the user time to read it, and a control to close it.
4. Tell screen reader users about each status message, but do not move the focus to it (WCAG 4.1.3).
5. Use a dialog only when the user must decide before the work continues.\
   Do not open a dialog from a dialog.

## Screen states

1. Loading: see Feedback.
2. Empty: tell why the view is empty, and give the next action.\
   Make a different empty state for the first use, for a search with no results, and for a list that the user cleared.
3. Error: tell what occurred and what the user can do, for example with a retry action.\
   Keep the data that the user entered, and the parts of the screen that work.
4. Offline: show which data is old, and which actions are not available.
5. No permission: tell why the user cannot see the content, and how to get access.

## Forms

1. Give each field a visible label.\
   Do not use the placeholder as the label.
2. Mark the required fields.\
   When most fields are required, mark the optional fields.\
   Tell the user which mark the form uses.
3. Ask only for the data that the product needs.\
   Do not ask for the same data two times in one process (WCAG 3.3.7).
4. Give each field the correct input type, keyboard, and autocomplete value.
5. Validate a field when the user leaves it, or when the user submits the form.\
   Do not show an error while the user types in a field for the first time.
6. Show each error next to its field, with text that tells how to correct it.\
   When the user submits a form with errors, move the focus to the first error or to a summary of the errors.
7. Do not clear the data that the user entered when an error occurs.
8. Let the user paste, and let password managers fill fields.\
   Do not make a sign-in that needs a memory test or a puzzle without an alternative (WCAG 3.3.8).
9. Put the fields of a form in one column.
