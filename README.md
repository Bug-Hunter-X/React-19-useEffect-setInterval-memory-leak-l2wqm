# React 19 useEffect setInterval Memory Leak

This repository demonstrates a common error in React 19 applications involving the `useEffect` hook and `setInterval`.  The example shows a memory leak because the interval is not properly cleaned up when the component unmounts, leading to continued updates after the component is no longer in the DOM.

## Bug Description
The `setInterval` function within the `useEffect` hook lacks a cleanup function.  This results in a memory leak, as the interval continues to run even after the component is unmounted.

## Solution
The solution involves returning a cleanup function from the `useEffect` hook.  This cleanup function clears the interval using `clearInterval` when the component unmounts or when the dependencies change.