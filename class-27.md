# React Testing and Deployment

## React Testing

1. **Snapshots** - Make assertions on the exact rendered markup (with content) at any state of the application.
1. **Render Testing** - Similar to snapshots, but allows for jQuery-like inspection of the virtual DOM tree
1. **Shallow Testing** - Executes and renders the called/container component, but does not compose children.
1. **Mounting** - Executes the full component and children. Allows for inspection of rendered Virtual DOM as well as the current state

**Sample** test for our counter component:

```
import React from 'react';
import renderer from 'react-test-renderer';
import Counter from '../../../../src/components/counter/counter.js';

describe('<Counter/> (Enzyme Test)', () => {
  it('is alive at application start', () => {
    let app = mount(<Counter />);
    expect(app.find('.count').text()).toBe('0');
  });

  it('can count up', () => {
    let app = mount(<Counter />);
    app.find('.up').simulate('click');
    expect(app.state('count')).toEqual(1);
    app.find('.up').simulate('click');
    expect(app.state('count')).toEqual(2);
  });

  it('can count down', () => {
    let app = mount(<Counter />);
    app.find('.down').simulate('click');
    expect(app.state('count')).toEqual(-1);
    app.find('.down').simulate('click');
    expect(app.state('count')).toEqual(-2);
  });

  it('visually displays proper polarity and value on the count element', () => {
    let app = mount(<Counter />);
    expect(app.find('.count.negative').exists()).toBeFalsy();
    expect(app.find('.count.positive').exists()).toBeFalsy();
    // Go to 1
    app.find('.up').simulate('click');
    expect(app.find('.count.positive').exists()).toBeTruthy();
    expect(app.find('.count').text()).toBe('1');

    // Down to zero
    app.find('.down').simulate('click');
    expect(app.find('.count').text()).toBe('0');
    expect(app.find('.count.negative').exists()).toBeFalsy();
    expect(app.find('.count.positive').exists()).toBeFalsy();

    // Down to -1
    app.find('.down').simulate('click');
    expect(app.find('.count.negative').exists()).toBeTruthy();
    expect(app.find('.count').text()).toBe('-1');
  });
});

describe('<Counter/> Core Component (Snapshot Test)', () => {
  it('renders right', () => {
    const component = renderer.create(<Counter />);
    let tree = component.toJSON();
    expect(tree).toMatchSnapshot();
  });
});
```

## Deployment

React in development mode uses a **node service** to create a live website that refreshes as you write code.
`npm run build`
This command, executed from the root folder of your React application will output a “static website” containing no more than the `index.html`, `.js` and `.css` files required to open your app.
