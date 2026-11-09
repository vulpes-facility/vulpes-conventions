# UI text

## Style

1. Write UI text in plain language: short sentences, common words, and the active voice.
2. Use the words of the user, not the words of the system or the code.\
   Do not show internal IDs or stack traces.\
   Show an error code only as extra information for support.
3. Use one term for each concept in the whole product.\
   Keep a glossary in the project.
4. Use the capitalization of the base design system or of the platform guideline.\
   When neither gives one, use sentence case.
5. When the product runs with more than one kind of input, use verbs that do not name a device.\
   Write "select", not "click" or "tap".
6. In each language, use one level of formality in the whole product.\
   For example, in Korean, use one speech level, such as 해요체, on all screens.

## Labels and messages

1. Label a button with a verb, and add the object when the verb alone is not clear.\
   For example, write "Save" or "Delete project".\
   Do not write "OK" or "Yes" when a verb can tell the result.
2. In an error message, tell what occurred and what the user can do.\
   Do not blame the user.\
   Put the message next to the cause.
3. In a confirmation dialog, ask the question in the title, and name the action on each button.\
   For example, use "Delete project?" with the buttons "Delete" and "Cancel".
4. In an empty state, tell why the view is empty and what the user can do.
5. Do not truncate important text.\
   When you must truncate text, show the full text in a tooltip, an expanded view, or a detail view.
6. Show dates, times, numbers, currencies, names, and addresses in the formats of the locale of the user.\
   Show times in the time zone of the user.

## Localization

1. Put one full sentence in each string.\
   Do not join parts of sentences, because the word order is different in other languages.\
   Use placeholders with names, for example `{count}` and `{name}`.
2. Write each plural form that each language needs.
3. Leave space for longer text.\
   A translation can be 30% longer than the English text, and a short label two or three times longer.\
   Let the layout wrap, and test it with pseudo-localization.
4. When the product supports a right-to-left language, mirror the layout ([`layout.md`](layout.md)).
5. Do not use flags for languages.\
   Show the name of each language in that language, for example "한국어" and "English".
