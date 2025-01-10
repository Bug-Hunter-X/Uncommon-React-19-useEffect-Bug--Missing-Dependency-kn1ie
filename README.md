# Uncommon React 19 useEffect Bug: Missing Dependency

This repository demonstrates a subtle bug related to the `useEffect` hook in React 19.  The issue highlights the importance of correctly specifying dependencies in the `useEffect` hook's second argument. Failure to do so can lead to unexpected re-renders and performance issues.

## The Bug
The `bug.js` file contains a component that uses `useEffect` to log the current count to the console. However, the `count` variable is missing from the dependency array. This causes the effect to run after every render, not just when the `count` changes.

## The Solution
The `bugSolution.js` file demonstrates the correct implementation. By adding `count` to the dependency array, the effect only runs when the `count` value changes, resolving the unexpected re-renders.

## How to reproduce
1. Clone the repo
2. Run `npm install`
3. Run `npm start`
4. Observe the console logs to see the difference between the buggy and fixed versions. 

## Additional Notes
This bug is more likely to surface in complex components where subtle dependencies are easily overlooked, leading to performance degradation and difficulty in debugging.  Always carefully consider the dependencies you add to the `useEffect` hook.