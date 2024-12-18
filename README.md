# Node.js Server Unresponsiveness Bug

This repository demonstrates a common issue in Node.js where a long-running synchronous operation in a request handler causes the server to become unresponsive.  The `bug.js` file contains the problematic code, while `bugSolution.js` shows the corrected version.

## Problem

Node.js is single-threaded, using an event loop to handle multiple requests concurrently.  If a request handler performs a long-running synchronous operation (like a `while` loop in this case), it blocks the event loop.  This prevents other requests from being processed, leading to unresponsiveness.

## Solution

The solution involves refactoring the long-running operation to be asynchronous.  This allows other requests to be processed while the long task runs in the background.  This usually involves using asynchronous functions, promises, or async/await syntax.