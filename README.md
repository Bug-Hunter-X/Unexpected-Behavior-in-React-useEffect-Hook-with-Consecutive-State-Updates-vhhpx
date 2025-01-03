# Unexpected Behavior in React useEffect Hook

This repository demonstrates a subtle bug related to consecutive state updates within a React `useEffect` hook.  The issue arises from the way React batches state updates. 

## Bug Description

The `MyComponent` component uses `useState` to track a count. The `useEffect` hook logs the count to the console after every render. The `handleClick` function increments the count twice in quick succession.  Due to React's state update batching, the `useEffect` hook might not capture the final expected state change.

## Solution

The solution involves either using `setTimeout` to guarantee state updates are separated, or better yet, leveraging functional updates to ensure the previous state is correctly used in the calculation.