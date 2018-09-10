
## Table of Contents

- [Code Formatting](#code-formatting)
- [Naming](#naming)
- [File Organization](#file-names)

## Code Formatting

For code formatting use [Prettier](https://github.com/prettier/prettier) with trailing commas set to 'es5' and single-quotes set to true.

## Naming

* Use the .js extension for React components.
* Use PascalCase for component names.
  * The component file name and css file name should have the same name as the component.
* Use Camel case for all other files, e.g. `withTooltip.js`
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
