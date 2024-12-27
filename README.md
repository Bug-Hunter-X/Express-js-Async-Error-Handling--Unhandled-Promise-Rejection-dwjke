# Express.js Async Error Handling Bug

This repository demonstrates a common error in Express.js applications related to unhandled promise rejections within asynchronous request handlers.  The `bug.js` file contains code that simulates an asynchronous operation.  If this operation fails, the error isn't properly handled, leading to a silent failure.  The solution is shown in `bugSolution.js`.

## How to Reproduce

1. Clone this repository.
2. Navigate to the directory.
3. Run `npm install express` to install the Express.js dependency.
4. Run `node bug.js`.
5. Observe that roughly half the time, the server will start but not handle the error correctly.  There will be an error message in the console, but the server won't crash. The client won't see an error.

## Solution

The `bugSolution.js` file demonstrates how to properly handle async errors using a central error handler.