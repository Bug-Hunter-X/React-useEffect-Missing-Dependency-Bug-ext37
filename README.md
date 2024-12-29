# React useEffect Missing Dependency Bug

This repository demonstrates a common yet subtle bug in React's `useEffect` hook:  a missing dependency leading to unexpected behavior. The provided `MyComponent` uses `setInterval` to update a counter, but the `useEffect` hook's dependency array is incorrect, resulting in the counter not updating properly because useEffect is only triggered once on mount. 

**Bug:** The `useEffect` hook is missing `count` in its dependency array. This means the `setInterval` is only set once on component mount and never cleaned up properly. Therefore, even though the counter is trying to update, useEffect will not re-render the component correctly.

**Solution:** Adding `count` to the dependency array ensures the effect runs whenever `count` changes, updating the `setInterval` correctly.