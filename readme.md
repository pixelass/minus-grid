# Minus minus grid
A grid powered by CSS custom properties


## Demo
[Demo on Codepen](https://codepen.io/pixelass/pen/yawEdy)

## Minus minus grid
"minus minus grid" uses the power of css variables a.k.a. custom properties. 
The results is a lightweight grid with a few lines of boilerplate and full flexibility.

#### Grid, Row, Column

This grid uses three different CSS selectors.

.grid
.row
.column
Endless nesting, same logic

A grid can be nested endlessly while preserving the column size

#### Advanced config

> Does not work in Safari!

```css
/* always 1/2 of its parent */
--m: calc(var(--columns) / 2);

/* always 3/4 of its parent */
--m: calc(var(--columns) / 4 * 3);

/* change per breakpoint */
--m: calc(var(--columns) / 4 * 3);
--l: calc(var(--columns) / 2);
--xl: calc(var(--columns) / 3);
```

## Set size as css variables
Since the cascade can/will break the logic, the variables are defined as inline styles. This allows a true scope and easy config.

#### Max values:

```css
.column {
  --m: 4
  --l: 8
  --xl: 12
 }
````

#### Default value:

```css
.column {
  --m: 1
  --l: var(--m)
  --xl: var(--l)
}
```

#### CSS context

each row opens a new grid. The column count is the same as the size of the parent column.

#### Pug (Jade) example

````jade
.grid // 12 columns
  .column(style={'--m': 4})
    .row // 4 columns
      .column(style={'--m': 'var(--columns)'})
```
