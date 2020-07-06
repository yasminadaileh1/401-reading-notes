# Custom Hooks

## what is hooks?
Hooks are JavaScript functions, but you need to follow two rules when using them. We provide a linter plugin to enforce these rules automatically:
1. Only Call Hooks at the Top Level
1. Only Call Hooks from React Functions

### Custom React Hooks
Hooks are just functions! Anything that is a function can become a Hook. I feel that the documentation on the ReactJS docs site is not simple enough. This is no knock on them, I just felt if I could try to explain it in even simpler terms, more people could benefit. So here is my stab at this one!

`useEffect`
```
useEffect(() => {
  document.title = `You clicked ${count} times`;
});
```

### React Hooks with Async-Await
```
function useAsyncHook(searchBook) {
  const [result, setResult] = React.useState([]);
  const [loading, setLoading] = React.useState("false");

  React.useEffect(() => {
    async function fetchBookList() {
      try {
        setLoading("true");
        const response = await fetch(
          `https://www.googleapis.com/books/v1/volumes?q=${searchBook}`
        );

        const json = await response.json();
        // console.log(json);
        setResult(
          json.items.map(item => {
            console.log(item.volumeInfo.title);
            return item.volumeInfo.title;
          })
        );
      } catch (error) {
        setLoading("null");
      }
    }

    if (searchBook !== "") {
      fetchBookList();
    }
  }, [searchBook]);

  return [result, loading];
}
```


### `useReducer`
An alternative to useState. Accepts a reducer of type (state, action) => newState, and returns the current state paired with a dispatch method. (If you’re familiar with Redux, you already know how this works.)
