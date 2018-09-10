
## Table of Contents

- [Code Formatting](#code-formatting)
- [Basic Rules](#basic-rules)
- [Component Usage](#component-usage)
- [Naming](#naming)
- [File Organization](#file-names)
- [File Imports](#file-imports)

## Code Formatting

For code formatting use [Prettier](https://github.com/prettier/prettier) with trailing commas set to 'es5' and single-quotes set to true.

## Basic Rules

* Use common components over creating a new one whenever possible
* Use utility methods and constants from `slope-shared` whenever possible

## Component Usage

* Always declare prop types
  * If a prop is not required, define a default prop whenever possible
  * Prop declarations should be in alphabetical order
* Props should be passed to components in alphabetical order
* Use stateless components whenever possible

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
  description: 'Default description',
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

## File Imports

*These have not been finalized*

* Imports are roughly separated in to the following blocks: external imports, actions and selectors, external components (e.g. `material-ui`), internal components, styles
* Lodash imports are at the top followed by React and PropTypes
* Absolute are above relative imports
* Default imports are above named imports
* Imports are sorted in ascending alphabetical order within the above rules
* Named imports are imported in alphabetical order

```js
// good
import { filter, isEmpty } from lodash;
import React, { Component } from 'react';
import cx from 'classnames';

import { createItem } from '../../actionCreators';
import { getItems } from '../../selectors';

import Header from '../Header';
import { IconButton } from '../../../common/components';

import styles from './CurrentView.css';
```
