# Node.js Server Unresponsiveness

This repository demonstrates a common Node.js issue: server unresponsiveness caused by a long-running synchronous operation blocking the event loop.  The `server.js` file contains the buggy code, while `serverSolution.js` provides a solution using asynchronous operations.

## Problem

The original server code performs a long-running computation (simulated here by a `while` loop) synchronously within the request handler.  This blocks the event loop, meaning that Node.js cannot process other requests during this time. The server appears to hang or become unresponsive.

## Solution

The solution involves using asynchronous operations (such as `setTimeout` or Promises) to avoid blocking the event loop. This ensures that Node.js can continue to handle other requests concurrently. 

## How to run the code

1. Clone the repository: `git clone ...`
2. Navigate to the repository directory: `cd ...`
3. Run the buggy server: `node server.js` (Observe the unresponsiveness)
4. Run the fixed server: `node serverSolution.js` (Observe responsiveness)