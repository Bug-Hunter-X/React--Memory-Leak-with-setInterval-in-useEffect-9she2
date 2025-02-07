# React: Memory Leak with setInterval in useEffect
This example demonstrates a common error in React: using setInterval inside useEffect without proper cleanup. This can lead to memory leaks and unexpected behavior.

## Bug
The `MyComponent` component uses setInterval to update the count every second. However, it lacks a cleanup function in useEffect to clear the interval when the component unmounts.  This means that even after the component is removed from the DOM, the interval continues to run, consuming resources.

## Solution
The solution is to return a cleanup function from the useEffect hook. This function will clear the interval when the component unmounts, preventing the memory leak.
