# Table of content
1. What is redux?



<br>
<br>

# Redux
* Redux is a global State container
* For now, I only researched `redux-toolkit`. The `@reduxjs/toolkit` package wraps around the core redux package, and contains API methods and common dependencies that we think are essential for building a Redux app.
* How to install `redux toolkit`?

<br>
<br>

# Environment Introduction
Install `redux toolkit`
```console
npm install @reduxjs/toolkit
```

<br>

* First Install the package.
* NEXT STEP: set up store. What do you mean set up store?
What is store?

<br>

### Store & Slice
* `STORE` : Store is where all the `global state` is stored. In detail, `store` actually contains `slice`.
* `slice`: what is slice? Slice contains `function` and `state` declaration. `Functions` - functions that can update state.
* First I have to set up state. After that I have to create a `slice` that contains state. I can define one state in one slice. But I can declare multiple value in one state like object.
```jsx
const [state, setState] = useState({
    valueOne: 'initial value',
    valueTwo: 'initial value',
  });
// this idea is used in redux alot.
```

<br>
<br>

### How to create store?
```javascript

```

# redux-research
What is a Reducer in Redux?

* In Redux, a reducer is like a function that manages the state of your application. Think of the state as the memory of your application, storing information about how things are at a given moment.

* A reducer is responsible for updating this state based on certain actions that occur in your app. Actions are like messages that tell the reducer what needs to change in the state.

<br>

What does a Reducer Look Like? <br>
A reducer is just a function. It takes two things as input:

1. Current State: This is how things are right now.
2. Action: This is like a command or instruction on what should change.

The reducer then processes the action and returns a new state that reflects the changes.

```javascript
// The initial state of your app
const initialState = {
  count: 0,
};

// The reducer function
const counterReducer = (state = initialState, action) => {
  // The action tells us what to do
  switch (action.type) {
    case 'INCREMENT':
      // If the action is to increment, return a new state with count increased
      return { count: state.count + 1 };
    case 'DECREMENT':
      // If the action is to decrement, return a new state with count decreased
      return { count: state.count - 1 };
    default:
      // If the action is unknown, return the current state unchanged
      return state;
  }
};

// Example usage:
// Imagine dispatching an action like { type: 'INCREMENT' }
const newState = counterReducer(initialState, { type: 'INCREMENT' });
console.log(newState); // { count: 1 }

```
<br>

<br>

what is Redux State Slice?
<br>
A Redux State Slice is a concept introduced by the @reduxjs/toolkit library to help organize and manage slices of your application state in a more modular way. 

<br>
<br>

```javascript

import { createSlice } from '@reduxjs/toolkit';

// Initial state for the counter slice
const initialState = {
  value: 0,
};

// Create a counter slice using createSlice
const counterSlice = createSlice({
  name: 'counter',  // Name of the slice
  initialState,     // Initial state
  reducers: {
    increment: (state) => {
      state.value += 1;
    },
    decrement: (state) => {
      state.value -= 1;
    },
  },
});

// Export the reducer and action creators
export const { increment, decrement } = counterSlice.actions;
export default counterSlice.reducer;












import React from 'react';
import { useDispatch, useSelector } from 'react-redux';
import { increment, decrement } from './path/to/your/counterSlice';

const CounterComponent = () => {
  // Step 1: Connect to the Redux store
  const dispatch = useDispatch();

  // Step 2: Access the state from the store
  const counter = useSelector((state) => state.counter.value); // Assuming 'value' is the key in your counter slice

  return (
    <div>
      <h1>Counter: {counter}</h1>
      {/* Step 3: Dispatch actions to update the state */}
      <button onClick={() => dispatch(increment())}>Increment</button>
      <button onClick={() => dispatch(decrement())}>Decrement</button>
    </div>
  );
};

export default CounterComponent;


```

<br>
<br>
<br>
<br>
<br>

# Fresh Start
## the flow of redux configuration
```javascript
import { createApi, fetchBaseQuery } from "@reduxjs/toolkit/query/react";

// creating API slice 
export const API = createApi({
  reducerPath: 'jsonServerApi',
  baseQuery: fetchBaseQuery({ baseUrl: 'https://reqres.in' }),
  tagTypes: ['product'],
  endpoints: (builder) => ({
    // Define your endpoint here
    getUsers: builder.query({
      query: () => 'api/users', // Specify the endpoint path
    }),
  }),
});

// Export the generated hook for the endpoint
export const { useGetUsersQuery } = API;

```
