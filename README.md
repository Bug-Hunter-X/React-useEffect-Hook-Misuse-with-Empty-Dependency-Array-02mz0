# React useEffect Hook Misuse
This example demonstrates a common mistake when using the `useEffect` hook in React. The problem lies in using an empty dependency array `[]` in combination with a conditional statement that depends on a state variable. This leads to the effect only running once on mount, ignoring subsequent state changes.

## Bug Description
The `useEffect` hook has an empty dependency array `[]`, which means it only runs once after the initial render. The conditional statement inside the effect checks if `count` is greater than 0. Because the effect only runs once, it only considers the initial value of `count`, which is 0. Hence, the log message never appears even after incrementing the count.

## Solution
Include the state variable `count` in the dependency array of `useEffect` so that it reruns whenever `count` updates.