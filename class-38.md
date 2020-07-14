# Redux - Asynchronous Actions

Three different **kinds** of actions:
1. An action informing the reducers that the **request began**.
2. An action informing the reducers that the request **finished successfully**.
3. An action informing the reducers that the request **failed**.

The user can select a **subreddit** to display:
1. `actions.js`
```
export const SELECT_SUBREDDIT = 'SELECT_SUBREDDIT'

export function selectSubreddit(subreddit) {
  return {
    type: SELECT_SUBREDDIT,
    subreddit
  }
}
```

`REQUEST_POSTS` action:
```
export const REQUEST_POSTS = 'REQUEST_POSTS'

function requestPosts(subreddit) {
  return {
    type: REQUEST_POSTS,
    subreddit
  }
}
```
dispatch `RECEIVE_POSTS`:
```
export const RECEIVE_POSTS = 'RECEIVE_POSTS'

function receivePosts(subreddit, json) {
  return {
    type: RECEIVE_POSTS,
    subreddit,
    posts: json.data.children.map(child => child.data),
    receivedAt: Date.now()
  }
}
```
#### Handling Actions

`reducers.js`
Use ES6 computed property syntax so we can update `state[action.subreddit]` with `Object.assign()` in a concise way. This:
```
return Object.assign({}, state, {
  [action.subreddit]: posts(state[action.subreddit], action)
})
```
OR
```
let nextState = {}
nextState[action.subreddit] = posts(state[action.subreddit], action)
return Object.assign({}, state, nextState)
```

When an **action creator returns a function**, that function will get executed by the **Redux Thunk middleware**. This function doesn't need to be *pure*; it is thus allowed to have side effects, including executing asynchronous API calls. 

#### What’s a thunk?!
A thunk is a function that wraps an expression to delay its evaluation.
```
// calculation of 1 + 2 is immediate
// x === 3
let x = 1 + 2;

// calculation of 1 + 2 is delayed
// foo can be called later to perform the calculation
// foo is a thunk!
let foo = () => 1 + 2;
```

#### Composition
Any return value from the inner function will be available as the return value of dispatch itself. This is convenient for orchestrating an asynchronous control flow with thunk action creators dispatching each other and returning Promises to wait for each other’s completion.



