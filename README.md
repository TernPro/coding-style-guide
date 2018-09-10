
## Table of Contents

- [Code Formatting](#code-formatting)
- [Component Usage](#component-usage)
- [Naming](#naming)
- [File Organization](#file-names)

## Code Formatting

For code formatting use [Prettier](https://github.com/prettier/prettier) with trailing commas set to 'es5' and single-quotes set to true.

## Component Usage

* Always declare prop types. If a prop is not required, define a default prop whenever possible.

* If the component has state, refs, or needs lifecycle menthods, use `class extends React.Component`
  * Declare state, default props, and prop types as static variables whenever possible
  * Alphabetize method names that aren't part of the Component Lifecycle

```js
// good
class Header extends React.Component {
  static propTypes = {
    name: PropTypes.string.isRequired,
  }
  
  static defaultProps = {
    name: "Default page",
  }
  
  state = {
    counter: 1,
  }
  
  componentDidMount() {
    // ...
  }
  
  handleClick = () => {
    // ...
  }
  
  render() {
    return (
      // ...
    );
  }
}
```

* For components that do not use state, refs, or lifecycle methods, use stateless components
  * Use regular functions, not arrow functions, for component declarations
  * Destructure params 

```js
// good
function Header({ name, description, ...props }) {
  return (
    // ...
  )
}

Header.propTypes = {
  name: PropTypes.string.isRequired,
  description: PropTypes.string,
};

Header.defaultProps = {
  description: "Default description",
};
```

## Naming

* Use the `.js` extension for React components
* Use PascalCase for component names: `TableHeader.js`
  * The component file name and css file name should have the same name as the component.
* Use Camel case for all other files: `withTooltip.js`
* Use Camel case for CSS classnames

```css
// bad
.lightbox-container {
  // ...
}

// good
.lightboxContainer {
  // ...
}
```

## File Organization

There should be no more than one component per file. Component file names are capitalized and match the name of the component inside. An index.js file is included for the default export.
