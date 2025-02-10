# JavaScript Closure Issue in setTimeout Loop

This repository demonstrates a common issue in JavaScript involving closures and the `setTimeout` function within a loop.  The expected behavior is to log the numbers 0 through 9 with a one-second delay between each. However, due to the way closures work in JavaScript, the code produces unexpected results.

## Problem
The problem arises because the `setTimeout` callback function doesn't capture the value of `i` at the time it's created within the loop. Instead, it captures the reference to the `i` variable. By the time `setTimeout` executes, the loop has already completed, and `i` will be its final value (10).

## Solution
The solution involves using an immediately invoked function expression (IIFE) to create a new scope for each iteration of the loop. This ensures that each callback captures its own copy of the `i` variable.

## How to Run
1. Clone the repository.
2. Open `bug.js` and `bugSolution.js` in a code editor.
3. Open your browser's developer console.
4. Run `bug.js` to observe the incorrect behavior.
5. Run `bugSolution.js` to see the corrected output.