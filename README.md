# Express.js Route Handler Missing Error Handling for Invalid User ID

This repository demonstrates a common error in Express.js route handlers:  the lack of proper error handling when dealing with user inputs.  The `bug.js` file showcases a route that fails to handle cases where the user ID is not a valid number.  The `bugSolution.js` file provides a corrected version with robust error handling.

## Bug

The bug lies in the `/users/:id` route. If a non-numeric ID is passed, `parseInt(userId)` will return `NaN`, causing the `find` method to fail silently or throw an error, leading to unexpected application behavior or crashes.

## Solution

The solution involves adding comprehensive error handling to gracefully manage invalid inputs. This involves checking if the parsed `userId` is a valid number and returning an appropriate HTTP error response (400 Bad Request) if not.