# Firebase onAuthStateChanged Unsubscribe Issue

This repository demonstrates a common issue encountered when using Firebase's `onAuthStateChanged` listener: memory leaks due to improper unsubscription.  The provided code snippet showcases the problem and its solution.

## Problem
The `onAuthStateChanged` listener, while useful for tracking authentication status, can cause memory leaks if not properly unsubscribed from when it's no longer needed.  This typically occurs when a component using the listener is unmounted.  The listener continues to run, consuming resources.

## Solution
The solution involves returning an unsubscribe function from the component or function using `onAuthStateChanged`. This function cleans up the listener when the component is unmounted, preventing memory leaks.  The corrected code demonstrates this best practice.

## How to Use
1. Clone the repository.
2. Install Firebase:  `npm install firebase`
3. Configure Firebase in `bug.js` and `bugSolution.js` with your project's configuration.
4. Run the code to observe the memory leak in `bug.js` and its resolution in `bugSolution.js`.