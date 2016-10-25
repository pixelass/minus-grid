# Minus minus grid
A grid powered by CSS custom properties

[![npm](https://img.shields.io/npm/v/minus-grid.svg)](https://www.npmjs.com/package/minus-grid)
[![Coveralls branch](https://img.shields.io/coveralls/pixelass/minus-grid.svg)](https://coveralls.io/github/pixelass/minus-grid)
[![bitHound Overall Score](https://www.bithound.io/github/pixelass/minus-grid/badges/score.svg)](https://www.bithound.io/github/pixelass/minus-grid)
[![Standard Version](https://img.shields.io/badge/release-standard%20version-brightgreen.svg)](https://github.com/conventional-changelog/standard-version)
[![Commitizen friendly](https://img.shields.io/badge/commitizen-friendly-brightgreen.svg)](http://commitizen.github.io/cz-cli/)  
[![Travis](https://img.shields.io/travis/pixelass/minus-grid.svg)](https://travis-ci.org/pixelass/minus-grid)
[![David](https://img.shields.io/david/pixelass/minus-grid.svg)](https://david-dm.org/pixelass/minus-grid)
[![David](https://img.shields.io/david/dev/pixelass/minus-grid.svg)](https://david-dm.org/pixelass/minus-grid#info=devDependencies&view=table)  
[![GitHub license](https://img.shields.io/github/license/pixelass/minus-grid.svg)](https://github.com/pixelass/minus-grid/blob/master/LICENSE)
[![GitHub issues](https://img.shields.io/github/issues/pixelass/minus-grid.svg)](https://github.com/pixelass/minus-grid/issues)
[![GitHub forks](https://img.shields.io/github/forks/pixelass/minus-grid.svg)](https://github.com/pixelass/minus-grid/network)
[![GitHub stars](https://img.shields.io/github/stars/pixelass/minus-grid.svg)](https://github.com/pixelass/minus-grid/stargazers)


## Demo
[Documentation](https://pixelass.github.io/minus-grid/)  
[Demo on Codepen](https://codepen.io/pixelass/pen/yawEdy)

## Minus minus grid
"minus minus grid" uses the power of css variables a.k.a. custom properties. 
The results is a lightweight grid with a few lines of boilerplate and full flexibility.

#### Grid, Row, Column

This grid uses three different CSS selectors.

* `.grid`
* `.row`
* `.column`


#### Endless nesting, same logic

A grid can be nested endlessly while preserving the column size

#### Custom naming
Generate a file with your own naming convention, using the SCSS files

#### Advanced config

> Does not work in Safari!

```css
/* always 1/2 of its parent */
--viewport-small: calc(var(--column-count) / 2);

/* always 3/4 of its parent */
--viewport-small: calc(var(--column-count) / 4 * 3);

/* change per breakpoint */
--viewport-small: calc(var(--column-count) / 4 * 3);
--viewport-medium: calc(var(--column-count) / 2);
--viewport-large: calc(var(--column-count) / 3);
```

## Set size as css variables
Since the cascade can/will break the logic, the variables are defined as inline styles. This allows a true scope and easy config.

#### Max values:

```css
--viewport-small: 4
--viewport-medium: 8
--viewport-large: 12
````

#### Default value:

```css
--viewport-small: 1
--viewport-medium: var(--viewport-small)
--viewport-large: var(--viewport-medium)
```

#### CSS context

each row opens a new grid. The column count is the same as the size of the parent column.

#### Pug (Jade) example

````jade
.grid // 12 columns
  .column(style={'--viewport-small': 4})
    .row // 4 columns
      .column(style={'--viewport-small': 'var(--column-count)'})
```
