# Context API

## Context

**Context** provides a way to pass data through the component tree **without having to pass props** down manually at every level.


#### When to Use Context
Context is designed to **share data** that can be considered `“global”` for a tree of React components, such as the current *authenticated user*, *theme*, or *preferred language*.
**Context** is primarily used when some **data needs to be accessible** by many components at different nesting levels. Apply it sparingly because it **makes component reuse** more difficult.


#### API

- `React.createContext`:
Creates a Context object. When React renders a component that subscribes to this Context object it will **read** the current **context value** from the **closest matching Provider** above it in the tree.
```
const MyContext = React.createContext(defaultValue);
```
The `defaultValue` argument is only used when a component does not have a matching Provider above it in the tree.

- `Context.Provider`:
Every Context object comes with a Provider React component that allows **consuming components to subscribe to context changes**.
```
<MyContext.Provider value={/* some value */}>
```
Accepts a `value` prop to be passed to consuming components that are descendants of this Provider. 

- `Class.contextType`:
The `contextType` property on a class can be assigned a Context object created by `React.createContext()`. This lets you **consume the nearest current value** of that Context type using `this.context`. You can reference this in any of the lifecycle methods including the render function.

- `Context.Consumer`:
A React component that subscribes to context changes. This lets you **subscribe to a context within a function** component.

- `Context.displayName`:
Context object accepts a displayName **string property**. React DevTools uses this string to determine what to **display for the context**.



##### `useContext()`
`const value = useContext(MyContext);`

**Accepts a context object** (the value **returned** from `React.createContext`) and returns the current context value for that context. The current context value is determined **by the value prop of the nearest `<MyContext.Provider>`** above the calling component in the tree.
When the nearest `<MyContext.Provider>` above the component **updates**, this Hook will **trigger a rerender with the latest context value passed** to that MyContext provider. Even if an ancestor uses `React.memo` or `shouldComponentUpdate`, a rerender will still happen starting at the component itself using `useContext`.


## Snackbars in React: An Exercise in Hooks and Context

#### Necessity for the Design System:
They are **small notifications** that show up on the screen when a user **performs an action**. They are not intrusive at all and **appear for just a brief moment**.

#### Globally Accessible
The state can be **localized** to a single centralized component. That same centralized component can be **responsible for rendering them**. There’s really no need for another component somewhere in the tree to hook into that state. The management of that **state** (**adding**, **removing**) needs to be **globally accessible**.



**Additional Resources** :partly_sunny:

**Bookmark / Skim** :star:

- [context api](https://reactjs.org/docs/context.html)
- [hooks and context example](https://medium.com/swlh/snackbars-in-react-an-exercise-in-hooks-and-context-299b43fd2a2b)
- [react context links](https://github.com/diegohaz/awesome-react-context)

