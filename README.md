# React useEffect Dependency Array Issue

This repository demonstrates a common error in React's `useEffect` hook: forgetting to include state variables in the dependency array.  This can lead to infinite loops and unexpected behavior.

## The Problem

The `bug.js` file shows an incorrect implementation of `useEffect`. The effect attempts to log the count, but it's not included in the dependency array (`[]`).  This means the effect runs on every render, causing an infinite loop because updating the state triggers re-renders.

## The Solution

The `bugSolution.js` file shows the corrected code.  The `count` variable is added to the dependency array (`[count]`). Now, the effect only runs when the `count` state changes. 

## How to Reproduce

1. Clone this repository.
2. Navigate to the project directory.
3. Run `npm install` to install dependencies.
4. Run `npm start` to start the development server.
5. Observe the console output in `bug.js` which shows infinite logs and in `bugSolution.js` that shows controlled logs. 

This example illustrates the importance of carefully considering the dependencies in your `useEffect` hooks.