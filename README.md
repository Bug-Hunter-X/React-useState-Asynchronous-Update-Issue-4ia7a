# React useState Asynchronous Update Issue

This repository demonstrates a common issue encountered when using React's `useState` hook.  Because state updates in React are asynchronous, logging the state value immediately after calling `setCount` may not reflect the updated value.  This example showcases the problem and provides a solution.

## Bug Description
The `MyComponent` displays a count and an increment button.  The intention is to log the updated count after incrementing.  However, due to the asynchronous nature of `useState`, the log often shows the *previous* count.

## Solution
The solution involves using functional updates with `setCount` and performing the logging operation in the `useEffect` hook after the state has had time to update.  This ensures that the logged value is the correct, updated count.