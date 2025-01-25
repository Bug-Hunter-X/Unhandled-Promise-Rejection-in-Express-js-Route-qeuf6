# Unhandled Promise Rejection in Express.js Route

This repository demonstrates a common error in Express.js applications: unhandled promise rejections.  The issue arises when an asynchronous operation within a route handler fails, and the error isn't properly caught.

The `bug.js` file showcases the problematic code.  The `bugSolution.js` file provides a corrected version.

## Problem
The original code attempts to fetch user data from a database. If the database operation fails, the promise rejects, leading to an unhandled rejection.  This often manifests as a silent failure or a crash depending on your process manager.

## Solution
The solution uses `try...catch` to handle potential errors during the database operation.  If an error occurs, a proper error response is sent to the client.

## How to Reproduce
1. Clone this repository.
2. Run `node bug.js` (Note: you'll need to adapt the database interaction to your specific setup, or replace it with a simulated error).
3. Observe the unhandled promise rejection or the failure to handle the error correctly.
4. Run `node bugSolution.js` to see the corrected behavior. 