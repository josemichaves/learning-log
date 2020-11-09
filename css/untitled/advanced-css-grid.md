# Advanced CSS Grid

```css
grid-template-areas: "a a a"
                     "b b b"           
                     "b b c";
```

Assign the cell to a class.



```css
justify-items: start;

```

It aligns the items inside their grid areas on the inline axis.



```css
justify-content: space-around;
```

 The CSS `justify-content` property defines how the browser distributes space between and around content items along the inline axis of a grid container.



```css
justify-self: left;
```

Specifies how a single element should position itself with respect to the row axis.



```css
align-items: center;
```

Specifies how individual elements should spread across the column axis.



```css
align-content: normal;
```

Specifies how groups of elements should spread across the column axis.



```css
align-self: end;
```

Specifies how a single element should position itself with respect to the column axis.



```css
grid-auto-rows: 50px 20%;
```

The `grid-auto-rows` CSS property specifies the size of an implicitly-created grid row track or pattern of tracks. Can take `minmax(minSize,maxSize)`.



```css
grid-auto-columns: 2fr;
```

Specifies the width of columns added implicitly to the grid.



```css
grid-auto-flow: dense;
```

 The `grid-auto-flow` CSS property controls how the auto-placement algorithm works, specifying exactly how auto-placed items get flowed into the grid.



### Implicit Grid vs Explcit Grid

 When we use `grid-template-columns` and `grid-template-rows` we create an Explicit Grid.  

However if we try and place an item outside of that grid the browser will create an Implicit Grid line or lines in order to hold that item.

