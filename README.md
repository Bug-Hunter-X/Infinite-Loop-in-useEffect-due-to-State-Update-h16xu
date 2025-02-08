# React useEffect Infinite Loop Bug

This repository demonstrates a common React bug where an infinite loop occurs due to improper usage of the `useEffect` hook.  The `useEffect` hook is designed to perform side effects, but if it modifies state in a way that triggers a re-render within the effect itself, an infinite loop results.

## Bug Description

The `bug.js` file contains a component that increments a counter using `useState` and logs the count in a `useEffect`.  However, the effect runs after every render, and the `setCount` call inside `handleClick` causes the component to re-render continuously, leading to an infinite loop. The console will show the 'Count updated' message repeating infinitely.

## Solution

The `bugSolution.js` file demonstrates the solution. The key is to use the dependency array in the `useEffect` hook correctly. By adding `[count]` as the dependency array, the effect only runs when the `count` variable changes.  This prevents the infinite loop.