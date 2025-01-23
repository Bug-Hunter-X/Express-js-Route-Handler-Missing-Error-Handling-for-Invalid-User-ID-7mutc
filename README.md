# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers: the lack of proper error handling when dealing with user inputs.  Specifically, this example shows a route that fetches a user by ID but fails to handle cases where the ID is not a valid number.

## Bug

The `bug.js` file contains the buggy code. The route handler attempts to parse the user ID as an integer using `parseInt()` without checking if the input is actually a number.  If the ID is not a number (e.g., a string), `parseInt()` will return `NaN`, leading to a potential crash or unexpected behavior.

## Solution

The `bugSolution.js` file provides a corrected version of the code that includes proper error handling.  The solution checks if `parseInt(userId)` is a valid number before attempting to use it. If not, it sends a 400 Bad Request error to the client.