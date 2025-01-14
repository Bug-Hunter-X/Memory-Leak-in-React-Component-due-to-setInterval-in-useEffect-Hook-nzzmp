# React useEffect setInterval Memory Leak

This repository demonstrates a common React bug involving memory leaks caused by improper usage of `setInterval` within the `useEffect` hook.  The `bug.js` file shows the faulty code. The `bugSolution.js` file demonstrates the correct implementation.

**Problem:** The original code fails to clear the interval when the component unmounts. This leads to the `setInterval` continuing to run indefinitely, even after the component is removed from the DOM, resulting in a memory leak. 

**Solution:** The solution includes a cleanup function inside the `useEffect` hook's return statement. This function, `clearInterval(intervalId)`, ensures that the interval is cleared when the component unmounts, preventing the memory leak.