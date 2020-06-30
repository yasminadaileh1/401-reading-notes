# Component Composition :eyes:

## Routing
- `react-router` can toggle visibility of components
- by using `Link` tags we can browse easier to components

`import { Route } from 'react-router-dom';`
```
<Link to="/">Home</Link>
<Link to="/stuff">Stuff</Link>
```

## Logical
```
// Dashboard Wrapper
//  - feeds the SearchForm some methods
//  - then feeds the results some data

<Dashboard>
  <SearchForm handler={this.doTheSearch} />
  <Results data={this.state.results} />
</Dashboard>

// .. Results Component
<ul>
  {this.props.data.map( (item,i) => <li key={i}>{item}</li> );
</ul>

```

## Using Logic-less Children
```
<Dashboard>
  render() {
    let listings = {this.state.results.map( (item,i) => <li key={i}>{item}</li> );
  }
  <SearchForm handler={this.doTheSearch} />
  <Results>
    { listings.map( listing => listing ) }
  </Results>
</Dashboard>

// Results Component

<ul>
  {this.props.children}
</ul>

```

**Additional Resources** :partly_sunny:

**Bookmark / Skim** :star:

- [react basics recap](https://www.freecodecamp.org/news/these-are-the-concepts-you-should-know-in-react-js-after-you-learn-the-basics-ee1d2f4b8030/)
- [props.children](https://codeburst.io/a-quick-intro-to-reacts-props-children-cb3d2fce4891)
- [browser router tutorial](https://blog.pshrmn.com/simple-react-router-v4-tutorial/)
- [composition vs inheritance](https://reactjs.org/docs/composition-vs-inheritance.html)
- [browser router api docs](https://reacttraining.com/react-router/web/api)

