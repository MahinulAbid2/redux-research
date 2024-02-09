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
<br>

# Destructing configureStore

<img src="https://github.com/MahinulAbid2/redux-research/assets/70069009/eb529dc5-ac37-437d-b095-48321bf33e67" style="width: 500px">
<br>
<img src="https://github.com/MahinulAbid2/redux-research/assets/70069009/620dd2b4-5664-4e5a-ad2f-25de97179459" style="max-width: 100%">

<br>

![image](https://github.com/MahinulAbid2/redux-research/assets/70069009/000d4053-dcab-4079-a9e0-0cae44143e58)












