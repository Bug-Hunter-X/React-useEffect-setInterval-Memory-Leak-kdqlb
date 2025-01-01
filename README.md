# React useEffect setInterval Memory Leak
This repository demonstrates a common error in React applications involving the use of `setInterval` within the `useEffect` hook.  The example shows a memory leak caused by the failure to clear the interval when the component unmounts, leading to continuously running intervals.
The `bug.js` file contains the erroneous code. The `bugSolution.js` file shows how to correctly implement `setInterval` within `useEffect` to prevent this memory leak.
## How to reproduce
1. Clone the repository
2. Run `npm install`
3. Run `npm start`
Observe the count increasing indefinitely even after the component is unmounted (not directly observable but causes memory leak).  The solution fixes this.
## Solution
The solution addresses the memory leak by using the return value of `useEffect` to clear the interval. This ensures that the interval stops when the component is unmounted or the dependency array changes.