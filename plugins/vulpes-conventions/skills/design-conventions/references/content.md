# UI text

## Style

1. Use the words of the user, not the words of the system or the code.\
   Do not show internal IDs or stack traces.
2. Use one term for each concept in the whole product, and keep a glossary in the project.
3. Use the capitalization of the base design system or of the platform, or sentence case when neither gives one.
4. When the product runs with more than one kind of input, write "select", not "click" or "tap".
5. In each language, use one level of formality in the whole product, for example 해요체 in Korean.

## Labels and messages

1. Label a button with a verb, and add the object when the verb alone is not clear.\
   Do not write "OK" or "Yes" when a verb can tell the result.
2. In an error message, tell what occurred and what the user can do, next to the cause.\
   Do not blame the user.
3. In a confirmation dialog, ask the question in the title, and name the action on each button.
4. When you must truncate important text, show the full text in a tooltip or a detail view.
5. Show dates, times, numbers, currencies, names, and addresses in the formats of the locale of the user.\
   Show times in the time zone of the user.

## Localization

1. Put one full sentence in each string, with named placeholders such as `{count}`.\
   Do not join parts of sentences, because the word order changes in other languages.
2. Write each plural form that each language needs.
3. Leave space for longer text: a short label can be two or three times longer in a translation.\
   Test the layout with pseudo-localization.
4. Do not use flags for languages.\
   Show the name of each language in that language.
