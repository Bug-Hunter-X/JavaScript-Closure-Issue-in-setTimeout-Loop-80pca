# JavaScript Closure Issue in setTimeout Loop

This repository demonstrates a common closure-related bug in JavaScript when using `setTimeout` within a loop. The issue arises because the `setTimeout` callback function doesn't capture the value of `i` at the time of its creation; instead, it captures the reference to the variable `i`. By the time the `setTimeout` callbacks execute, the loop has already completed, and `i` holds its final value (10).

## Bug
The `bug.js` file contains the erroneous code. Running this code will print '10' ten times to the console, rather than the expected sequence of 0 through 9.

## Solution
The `bugSolution.js` file provides a corrected version using an immediately invoked function expression (IIFE) to create a new scope for each iteration, capturing the current value of `i` correctly.