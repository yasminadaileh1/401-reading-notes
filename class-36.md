# Application State with Redux

**Redux** is a **predictable state container** for JavaScript apps. With **Redux** we can **managing state** and this requires the combination of 3 distinct aspects into a **“Store”** which is:
- State
- Actions 
- Reducers 


### Redux principle:
1. Have a single source of truth: The **state** of your whole application is stored in an object tree within a single Redux store.
2. The only way to change the state is to emit an action, an **object** describing what happened.
3. To specify how the state tree is transformed by actions, you write pure **reducers**.


### installing:
`yarn add redux` run it in command line interface (CLI).

**Redux Reducer** is just a function that takes in two parameters. The first being the `STATE` of the app, and the other the `ACTION` .


### Redux Store:
The **“store”** is where your application state is, React uses **“reducers”** to **hold and manage state**, Reducers typically manage just **one part** of the larger application state. Reducers always **“Hear”** that an action was **dispatched**, and use whatever `“payload”` they receive to do their work.

We use a store to “bring it all together” … in the store, you declare what middleware you may need and the reducers that you’ll use to manage your state data


```
import { createStore, combineReducers, applyMiddleware } from 'redux';

import cartReducer from './reducers/cart.js';

let reducers = combineReducers({
  cart: cartReducer,
});

export default () => createStore(reducers);
```

In this example, when the `‘Start Shopping’` button is clicked, it runs a method called `this.props.initializeTheCart()`.

This method is declared in the `mapDispatchToProps` function as a pointer to the `newCart()` method in the actions file.

When you do this, you get to use `this.props.initializeTheCart` as a method. That’s what the mapper does for you, along with mapping the reducers’s state to `this.props` with the key that you specified.


### Additional Resources :pager:


**Videos** :smirk:

- [Dan Abramov Redux Tutorials](https://egghead.io/courses/getting-started-with-redux)


**Bookmark / Skim** :star:

- [worlds easiest guide to redux](https://www.freecodecamp.org/news/understanding-redux-the-worlds-easiest-guide-to-beginning-redux-c695f45546f6/)
- [testing with redux and enzyme](https://medium.com/netscape/testing-a-react-redux-app-using-jest-and-enzyme-b349324803a9)
- [testing reducers](https://medium.com/@netxm/testing-redux-reducers-with-jest-6653abbfe3e1)
- [Redux Docs](https://redux.js.org/)
- [enzyme-redux npm module](https://www.npmjs.com/package/enzyme-redux)
- [middleware tests with a mock store](https://gist.github.com/johncokos/4902683c8e33ed38fb2ba066b8764831)