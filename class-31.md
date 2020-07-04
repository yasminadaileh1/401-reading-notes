# Hooks API :sunglasses:

Hooks are JavaScript functions, with impose additional **rules** :hand: :
1. Hooks must be named with a `use` prefix.
2. Only call Hooks at the top level.
3. Only call Hooks from React function components.

## Built In Hooks :new_moon_with_face:
`useState()`
```
import React, { useState } from 'react';

function Example() {
  // Declare a new state variable, which we'll call "count"
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
}
```

### What is a Hook? :expressionless:
A Hook is a **special function** that lets you `“hook into”` React features. For example, `useState` is a Hook that lets you **add React state to function components**.

### When would I use a Hook? :sparkles:
You can use a Hook inside the existing function component.

## State Hook :star:
```
import React, { useState } from 'react';

function Example() {
  // Declare a new state variable, which we'll call "count"
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
}
```

`useState` is a Hook, We call it inside a function component to **add some local state** to it. React will preserve this state between **re-renders**.
`useState` returns a pair:
1. the **current state value**.
1. **function** that lets you update it. 

You can call this function from an event handler or somewhere else. It’s similar to this`.setState` in a class, except **it doesn’t merge the old and new state together**.
