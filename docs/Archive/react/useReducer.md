---
sidebar_position: 3
---

# useReducer


In React, the useReducer hook is a powerful tool for managing state in a more complex or advanced manner. It allows you to handle state updates through a reducer function, similar to how Redux manages state in a predictable way.

Let's consider a simple example of a counter using useReducer:

```JSX
import React, { useReducer } from 'react';

const initialState = { count: 0 };

const reducer = (state, action) => {
  switch (action.type) {
    case 'INCREMENT':
      return { count: state.count + 1 };
    case 'DECREMENT':
      return { count: state.count - 1 };
    case 'RESET':
      return { count: 0 };
    default:
      throw new Error(`Unhandled action type: ${action.type}`);
  }
};

const Counter = () => {
  const [state, dispatch] = useReducer(reducer, initialState);

  const increment = () => {
    dispatch({ type: 'INCREMENT' });
  };

  const decrement = () => {
    dispatch({ type: 'DECREMENT' });
  };

  const reset = () => {
    dispatch({ type: 'RESET' });
  };

  return (
    <div>
      <h1>Counter: {state.count}</h1>
      <button onClick={increment}>Increment</button>
      <button onClick={decrement}>Decrement</button>
      <button onClick={reset}>Reset</button>
    </div>
  );
};

export default Counter;

```

In this example, we define an initial state object { count: 0 } and a reducer function that handles state updates based on different action types.

The useReducer hook is called, taking the reducer function and the initial state as arguments, and it returns the current state and a dispatch function to trigger state updates.

Inside the component, we define three functions: increment, decrement, and reset. Each function calls the dispatch function with the appropriate action type, which is then handled by the reducer.

When the actions are dispatched, the reducer function is invoked with the current state and the action. It then performs the state update based on the action type using a switch statement.

Finally, the state count is rendered in the JSX using {state.count}.

The useReducer hook allows you to manage more complex state logic with ease. It provides a centralized way to handle state updates, making your code more maintainable and predictable. By using the reducer pattern, you can separate state management concerns and handle them in a single function, resulting in cleaner and more scalable code.