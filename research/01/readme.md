Information gathered from : https://redux-toolkit.js.org/tutorials/typescript

<br>
<br>

# Redux setup 
<b> Redux setup can be devided into 3 parts. `Ofcurse it's for typescript` </b>
* Define Root State and Dispatch Types
* Define Typed Hooks
* Define Slice State and Action Types

<br>

Now the question is what is 
* what is `Root State`?
* What do I mean by `typed hooks`?

<br>

### What is Root State? 
* `Root` - means <b>Main</b>
* I think <b>root state</b> is a term used in `redux`.
* IN GENENRAL, a `state` is limited to the React `individual component`. Means a state cannot be accessed outside of the individual component.
* Whereas Redux creates a `global state` which can be accessed by every component.
* The source or `global state` is called rootstate.
Root state looks something like this:
```typescript
mport { configureStore } from '@reduxjs/toolkit'
// ...

export const store = configureStore({
  reducer: {
    posts: postsReducer,
    comments: commentsReducer,
    users: usersReducer,
  },
})
```

<br>

# One important thing in main.tsx
```typescript
import React from 'react'
import ReactDOM from 'react-dom/client'
import { RouterProvider } from "react-router-dom";
import router from './routeHandler.tsx';
import { store } from './store/store.tsx'
import { Provider } from 'react-redux'  // have to import Provider from redux in implement i


ReactDOM.createRoot(document.getElementById('root')!).render(
  <React.StrictMode>
    <Provider store={store}>
      <RouterProvider router={router} />
    </Provider>
  </React.StrictMode>,
)
```

<br>
<br>

# Destructing configureStore

<img src="https://github.com/MahinulAbid2/redux-research/assets/70069009/eb529dc5-ac37-437d-b095-48321bf33e67" style="width: 500px">
<br>
<img src="https://github.com/MahinulAbid2/redux-research/assets/70069009/620dd2b4-5664-4e5a-ad2f-25de97179459" style="max-width: 100%">

<br>

![image](https://github.com/MahinulAbid2/redux-research/assets/70069009/000d4053-dcab-4079-a9e0-0cae44143e58)
<br>

![image](https://github.com/MahinulAbid2/redux-research/assets/70069009/01beaf6c-f129-42c5-9901-f08b56b86b3f)

<br>

![image](https://github.com/MahinulAbid2/redux-research/assets/70069009/c4c3eb39-3993-43bf-b6ff-4de16c3355fa)
















