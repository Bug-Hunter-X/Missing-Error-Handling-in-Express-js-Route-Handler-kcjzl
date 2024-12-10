# Missing Error Handling in Express.js Route Handler

This repository demonstrates a common error in Express.js route handlers: missing error handling for invalid input.  Specifically, the `/users/:id` route fails to handle cases where the `id` parameter is not a valid integer.

## Bug Description
The provided code attempts to directly parse the `id` parameter as an integer using `parseInt()`. If the parameter is not a number (e.g., a string or a special character), `parseInt()` will return `NaN`, which will cause the `find()` method to fail silently, potentially leading to unexpected behavior or crashes.

## Bug Solution
The solution involves adding explicit error handling to check if the parsed `userId` is actually a number. If it is not, a appropriate error response (e.g., 400 Bad Request) is returned to the client.