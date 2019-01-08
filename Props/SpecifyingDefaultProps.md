# Specifying defaultProps in functional and class components

In React we can define the default properties and we can do it in only a few lines of code. Default props come in handy if we need to make sure that a component's props appear a certain way, regardless of whether a parent component passed anything down to them.

You can specify default props by following this syntax:

`Component.defaultProps = { propName: 'Default value' }`

The defaultProps property should be set to an object representing the default props for the component, outside of the class body, as shown in the following code snippet:

```
class Phone extends React.Component {
  render() {
    // ...
  }
}

// Set default props
Phone.defaultProps = {
  numbers: [1, 2, 3, 4, 5, 6, 7, 8, 9, 0],
  power: "on"
}
```

As with class components, you can set default props on a functional component (by adding a static property named defaultProps):

```
function Phone = (props) => {
  render() {
    // ...
  }
}

// Set default props
ThemedButton.defaultProps = {
  numbers: [1, 2, 3, 4, 5, 6, 7, 8, 9, 0],
  power: "on"
}
```

For one more concrete example, let's say you want to greet somebody, but you don't yet know their name. I got this from the [React Doc for defaultProps](https://reactjs.org/docs/typechecking-with-proptypes.html#default-prop-values):

```
class Greeting extends React.Component {
  render() {
    return (
      <h1>Hello, {this.props.name}</h1>
    );
  }
}

// Specifies the default values for props:
Greeting.defaultProps = {
  name: 'Stranger'
};
```

Now, on the screen, we will see the phrase `Hello, Stranger`. Without defaultProps we would see a blank space.
