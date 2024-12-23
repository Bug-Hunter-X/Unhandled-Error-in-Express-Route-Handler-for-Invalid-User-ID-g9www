# Express.js Route Handler Error Handling Bug

This repository demonstrates a common error in Express.js route handlers:  lack of proper error handling for invalid input.  The `bug.js` file shows the buggy code, while `bugSolution.js` provides the corrected version.

**Bug:** The route `/users/:id` attempts to parse the `id` parameter as an integer.  If the `id` is not a number (e.g., a string or special character), `parseInt(userId)` returns `NaN`, leading to a potential crash or unexpected behavior depending on how the application is designed.  The current code doesn't handle this error effectively. 

**Solution:** The `bugSolution.js` file addresses this by adding robust error handling.  It checks for the validity of `userId` before attempting to find the user in the `users` array.  If `userId` is invalid, a relevant error message is returned with a 400 Bad Request status code.