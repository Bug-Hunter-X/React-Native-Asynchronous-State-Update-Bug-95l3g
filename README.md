# React Native Asynchronous State Update Bug

This repository demonstrates a common error in React Native related to asynchronous state updates.  When updating state based on the previous state, directly accessing `this.state` can lead to stale closures, resulting in unexpected behavior.  The solution provided uses the functional update pattern to ensure the state is updated correctly.

## Bug Description

The bug occurs when attempting to increment a state variable using the previous state value without using the functional update pattern. Because state updates are asynchronous, the value of `this.state` might be outdated by the time the `setState` function is called, leading to incorrect updates.

## Solution

The solution utilizes the functional update pattern, passing a function to `setState` that takes the previous state as an argument and returns the new state. This guarantees that the latest state is always used, preventing stale closure issues.

## How to Reproduce

1. Clone the repository.
2. Run `npm install`.
3. Run the app (using a React Native environment).
4. Observe the incorrect increment behavior in the initial `bug.js` implementation.
5. Switch to `bugSolution.js` to see the correct implementation.
