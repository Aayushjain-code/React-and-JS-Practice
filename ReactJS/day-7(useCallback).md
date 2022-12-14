### Day-7 useCallback- Avoid unnecessary re-renders with useCallback

#### CodeSandbox Link : https://codesandbox.io/s/day-7-usecallback-s2z2pj

π Avoid unnecessary re-renders with useCallback ! π

βοΈ Usage
    πββοΈ Skipping re-rendering of components
    π Updating state from a memoized callback
    π₯ Preventing an Effect from firing too often
    π οΈ Optimizing a custom Hook     


βοΈ By default, when a component re-renders, React re-renders all of its children recursively..

π By wrapping a function in useCallback, you ensure that itβs the same function between the re-renders (until dependencies change).  

π― The difference between useMemo and useCallback.
    π useMemo caches the result of calling your function
    π useCallback caches the function itself. Unlike useMemo, it does not call the function you provide. Instead, it caches the function you provided.


Code Example: 

```
import React, { useState, useCallback } from "react";

export default function App() {
  const [count, setCount] = useState(0);

  const onClick = useCallback((c) => {
    console.log("update!");
    setCount(c);
  }, []);

  return (
    <div>
      <h1>Count: {count}</h1>
      <button onClick={() => onClick(count + 1)}>Increase Count</button>
    </div>
  );
}
```
