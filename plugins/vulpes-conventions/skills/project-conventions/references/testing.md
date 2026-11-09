# Testing

Write the tests that protect a behavior, and no others.

1. Test the behavior that callers and users see, through the public API.\
   Do not test private functions or the inner structure of the code.
2. When you fix a bug, first write a test that fails because of the bug.\
   Then fix the bug.
3. Do not write a test for:\
   a. The framework, a library, or generated code.\
   b. Code with no logic, for example a field mapping or a getter.\
   c. A behavior that a different test already checks.\
   d. A large output, as a snapshot.
4. Use test doubles only at the boundary of the process: external APIs, the clock, and random values.
5. Do not add a test only to make the coverage higher.
6. Do not skip, weaken, or delete a failing test to make the checks pass.\
   Delete a test only when the behavior that it checks no longer exists.
