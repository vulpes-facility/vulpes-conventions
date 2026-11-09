# Components

## Spec

1. When the base design system has the component, use its spec.
2. For a new component, write the anatomy, the variants, the states, and the tokens.\
   Also write its behavior with each input and with a screen reader, and the limits of its content.

## States and actions

The states of a component are enabled, hover, focus, pressed, selected, disabled, loading, error, and read-only.

1. Show a focus indicator for keyboard focus.\
   Make it at least 2 CSS px thick, with a contrast ratio of at least 3:1 with the colors next to it.
2. Show the selected, checked, and error states with a mark, an icon, or text, not only with a color.
3. Give each view one primary action at most.
4. For an action that deletes or changes data, give an undo when you can.\
   Ask for a confirmation only when the action cannot be undone.
5. Do not disable the submit button of a form to show that the data is not correct.\
   Let the user submit, then show what to correct.
6. When a control is disabled, tell the reason when you can.

## Feedback

1. Show a snackbar only for a short status that needs no action.\
   Do not make it the only path to an action.
2. Use a dialog only when the user must decide before the work continues.\
   Do not open a dialog from a dialog.

## Screen states

1. Empty: tell why the view is empty, and give the next action.\
   Make a different empty state for the first use, for a search with no results, and for a cleared list.
2. Error: tell what occurred and what the user can do.\
   Keep the data that the user entered, and the parts of the screen that work.
3. Offline: show which data is old, and which actions are not available.
4. No permission: tell why the user cannot see the content, and how to get access.

## Forms

1. Give each field a visible label.\
   Do not use the placeholder as the label.
2. Mark the required fields, or the optional fields when most fields are required.
3. Validate a field when the user leaves it, or when the user submits the form.\
   Do not show an error while the user types in a field for the first time.
4. Show each error next to its field.\
   After a submit with errors, move the focus to the first error or to a summary of the errors.
5. Do not clear the data that the user entered when an error occurs.
6. Put the fields of a form in one column.
