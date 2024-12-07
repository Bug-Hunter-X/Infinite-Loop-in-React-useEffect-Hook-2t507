# React useEffect Infinite Loop Bug

This repository demonstrates a common bug in React applications involving the `useEffect` hook. The bug causes an infinite loop due to a missing dependency in the `useEffect` hook's dependency array.

## Bug Description

The `MyComponent` component uses the `useState` hook to manage a count variable. The `useEffect` hook is used to log the current value of `count` to the console. However, the dependency array for the `useEffect` hook is missing `count`, causing the effect to run after every render, regardless of whether `count` has changed. This leads to an infinite loop, as the effect updates `count`, triggering another render and another execution of the effect.

## Bug Solution

The solution is to include `count` in the dependency array of the `useEffect` hook. This ensures that the effect only runs when `count` changes. 

## How to reproduce

1. Clone the repository.
2. Navigate to the project directory.
3. Run `npm install` to install the dependencies.
4. Run `npm start` to start the development server.
5. Observe the infinite loop in the console.

## How to fix

1. Include `count` in the dependency array of the `useEffect` hook.

## Lessons Learned

This bug highlights the importance of carefully considering the dependencies of `useEffect` hooks. Missing dependencies can lead to unexpected behavior and performance issues. Always carefully specify the dependencies to ensure that your effects only run when necessary. 