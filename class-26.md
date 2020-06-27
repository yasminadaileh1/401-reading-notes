# Component Based UI

Component based **UI** systems like `React`, `Angular`, `Vue` and the like all operate on similar architectural principles.
 the application is a **composition of components** that work together to make the application work.
 
## React
```
const element = () => {
  return {
    <h1 className="greeting">
      Hello, world!
    </h1>
  }
);
```

```
const element = React.createElement(
  'h1',
  {className: 'greeting'},
  'Hello, world!'
);
```

 
  **JSX** it is a syntax extension to JavaScrip, and produces React `“elements”`.
  **React** embraces the fact that rendering logic is inherently coupled with other UI logic: how events are handled, how the state changes over time,
  and how the data is prepared for display.
  
  ### Embedding Expressions in JSX
  ```
  const name = 'Josh Perez';
const element = <h1>Hello, {name}</h1>;

ReactDOM.render(
  element,
  document.getElementById('root')
);
```

```
function formatName(user) {
  return user.firstName + ' ' + user.lastName;
}

const user = {
  firstName: 'Harper',
  lastName: 'Perez'
};

const element = (
  <h1>
    Hello, {formatName(user)}!
  </h1>
);

ReactDOM.render(
  element,
  document.getElementById('root')
);
```
