# React 19 useEffect Bug

This repository demonstrates a common bug in React 19 where the `useEffect` hook runs after every render, even when it doesn't depend on any state or props. This can lead to performance issues and unexpected behavior.

## Bug Description

The `useEffect` hook in the `MyComponent` component is designed to log a message to the console after every render. In React 18 and earlier versions, this would not cause unnecessary re-renders. However, in React 19, the effect runs on every state update causing performance problems.

## Bug Solution

The solution involves adding a dependency array to the `useEffect` hook. This ensures that the effect only runs when one of the dependencies changes. In this case, the effect doesn't depend on any values, so we pass an empty array as the second argument. This ensures the effect only runs once after the initial render. 

## How to Reproduce

1. Clone this repository.
2. Run `npm install` to install the dependencies.
3. Run `npm start` to start the development server. 
4. Observe the console logs. The logs show that the effect is executed after every state update.