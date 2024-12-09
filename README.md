# Node.js Server Hang on Delayed Response

This repository demonstrates a common issue in Node.js servers: hanging on delayed responses.  When a request takes longer than expected, especially with asynchronous operations, the server can appear to freeze. This is because Node.js uses a single-threaded event loop.  If a long-running operation blocks the event loop, no other requests can be processed.

## Bug

The `bug.js` file contains a simple Express.js server that simulates a 5-second delay before sending a response. This delay can cause the server to hang when multiple requests are made.

## Solution

The `bugSolution.js` file demonstrates a solution using the `setTimeout` method with a short timeout and a mechanism for tracking the response. This prevents the server from becoming unresponsive.