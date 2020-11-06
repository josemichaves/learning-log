# CSS Grid

```css
display: grid;
```

Set the container as the container grid.



```css
grid-template-columns: <10px 200px 2fr>;
```

Set the columns of the grid, and the size, can also be used the `repeat(<times>, <size>)` to make a pattern.



```css
grid-template-rows: <520px 50%>;
```

Set the roed of the grid, and the size, can also be used the `repeat(<times>, <size>)` to make a pattern.



```css
grid-template: <rows> / <columns>;
```

Shorthand for defining `grid-template-rows` and `grid-template-columns` at the same time.



```css
grid-gap: <20px>;
```

Blank space between rows \(can be achieved only the gaps for the rows with `row-gap:` \) and columns \(can also be achieved only columns with `column-gap:` \). 



```css
grid-row-start: <2>;
```

The row where the item will start.



```css
grid-row-end: <span 3>;
```

The row where the item will span, can be a numerical value, that means the row or a `span<2>` that means the row will span the especified number.



```css
grid-column-start: <5>;
```

The column where the item will start.



```css
grid-column-end: <8>;
```

The column where the item will span, can be a numerical value, that means the column or a `span<5>` that means the column will span the especified number.



```css
grid-area: <2 / 1 / span 3 / span 6>;
```

The combination of `grid-row-start` `grid-row-end` `grid-column-start` `grid-column-end` in one line.

The syntax is `grid-area: <grid-row-start> / <grid-column-start> / <grid-row-end> / <grid-column-end>;`



```css
Span
```

![](../../.gitbook/assets/grid_lines%20%282%29.png)

If we use the `grid-column: 1 / 3;` we're going to use the 1st and 2nd cell of the grid, thats beacuse we use the start lines of the cell as reference. Although if we use `grid-column: span 3;` we'll use the 1st cell until the 3rd cell, thats because he `span` declares that we'll use three cells on this column.

