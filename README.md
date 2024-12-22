# Express.js Route Handler Missing Return Statement

This repository demonstrates a common error in Express.js route handlers: missing a `return` statement within an `if` condition.  This can lead to unexpected behavior, as subsequent code in the handler will still execute even if the condition is met.

The `bug.js` file contains the problematic code. The `bugSolution.js` file shows the corrected code.

## Bug

In the `bug.js` file, the route handler checks if a user exists. If not, it sends a 404 response. However, it's missing a `return` statement before `res.send(user)`, resulting in the 404 response being sent, and then the `res.send(user)` response will also be sent after, which is unexpected and potentially problematic.