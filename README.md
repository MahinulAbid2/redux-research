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
