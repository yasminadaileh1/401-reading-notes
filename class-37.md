# Redux - Combined Reducers

### Using combineReducers
`combineReducers` is simply a utility **function** to simplify the most common use case when writing Redux reducers. `CombineReducers` enforces several **rules** to help users avoid common errors. `CombineReducers` will call each **slice** reducer with its current slice of state and the current `action`, giving the slice reducer a chance to **respond** and **update** its **slice of state** if needed.

### Defining State Shape
There are two ways to define the initial shape and contents of your store's state:
1. `createStore`.
2. return the **initial state** value when the state argument is `undefined`.

**Example** of how use of ES6 object literal shorthand with `combineReducers` can **define the state** shape:
```
// reducers.js
export default theDefaultReducer = (state = 0, action) => state

export const firstNamedReducer = (state = 1, action) => state

export const secondNamedReducer = (state = 2, action) => state

// rootReducer.js
import { combineReducers, createStore } from 'redux'

import theDefaultReducer, {
  firstNamedReducer,
  secondNamedReducer
} from './reducers'

// Use ES6 object literal shorthand syntax to define the object shape
const rootReducer = combineReducers({
  theDefaultReducer,
  firstNamedReducer,
  secondNamedReducer
})

const store = createStore(rootReducer)
console.log(store.getState())
// {theDefaultReducer : 0, firstNamedReducer : 1, secondNamedReducer : 2}
```

 The `state` produced by `combineReducers()` namespaces the states of each reducer under their **keys** as passed to `combineReducers()`. You can control state key names by using different keys for the reducers in the passed object.


**Videos** :smirk:

- [Multiple Reducers Example](https://www.youtube.com/watch?v=gBER4Or86hE)


**Bookmark / Skim** :star:

- [Redux Docs: Using Combined Reducers](https://redux.js.org/recipes/structuring-reducers/using-combinereducers/)
- [Redux Docs: Combined Reducer Syntax](https://redux.js.org/api/combinereducers/)