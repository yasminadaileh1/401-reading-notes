# Props and State 

## Forms and Inputs

**Form** elements in React maintain **internal state** like stateful child components, the creation of a **parent component** manages the state for all child components of the form and passes any necessary state down into it’s inputs through the use of `props`.

#### Props

IIt's a components accept **arbitrary inputs** the syntax of the `porps` looks like **HTML** attributes, and it's equivalent of function params. `Props` is the name of the **object** passed into a component constructor and any prop added to a component in the JSX will be accessible as a **property** on `props`. After props is passed into the constructors super function, they are **available** on the context by using `this.props`.

**Example**:

```
// this is the way we get to use them
const element = (
  <h1 className="greeting">
    Hello, world!
  </h1>
);
```
```
// what’s actually happening under the hood
const element = React.createElement(
  'h1',
  {className: 'greeting'},
  'Hello, world!'
);
```
### What are components? :thought_balloon:
component is a JavaScript class or function that optionally **accepts inputs** like *properties(props)* and **returns** a *React element*

Components can be written using ES6 **arrow function**
`const Greeting = () => <h1>Hello World today!</h1>;`

This is a **functional component** (called Greeting) that takes **no props** and **returns an H1** tag.
**nature** of functional components:
- **Functional** because they are **basically functions**.
- **Stateless** because they do **not hold or manage state**.
- **Presentational** because all they do is **output UI elements**.


Components can also be written using ES6 **classes**
```
class Greeting extends React.Component {
  render(){
    return <h1>Hello World Today!</h1>;
  }
}
```
**nature** of classes components:
- **Class** because they are basically **classes**
- **Smart** because they can **contain logic**
- **Stateful** because they can **hold or manage local state**
- **Container** because they usually **hold/contain numerous** other (mostly functional) **components**


`setState()` schedules an **update** to a component’s **state object**. When state changes, the component responds by **re-rendering**.

**Additional Resources** :partly_sunny:

**Bookmark / Skim** :star:

- [setState explained](https://css-tricks.com/understanding-react-setstate/)
- [handling events](https://reactjs.org/docs/handling-events.html)
- [forms](http://reactjs.org/docs/forms.html)
- [state and lifecycle](https://reactjs.org/docs/state-and-lifecycle.html)
- [components and props](https://reactjs.org/docs/components-and-props.html)
