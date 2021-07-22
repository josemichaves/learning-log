# Units

CSS has several different units for expressing a length.

```css
h1 {
  font-size: 60px;
}

p {
  font-size: 25px;
  line-height: 50px;
}
```

We have two main groups of sizes in CSS

## Absolute lengths

The following are all absolute length units — they are not relative to anything else, and are generally considered to always be the same size.

| Unit | Name |
| :--- | :--- |
| cm | Centimetres |
| mm | Millimetres |
| Q | Quarter-millimetres |
| pc | Picas |
| pt | Points |
| px | Pixels |

## Relative lengths

Relative length units are relative to something else, perhaps the size of the parent element's font, or the size of the viewport. The benefit of using relative units is that with some careful planning you can make it so the size of text or other element scales relative to everything else on the page. Some of the most useful units for web development are listed in the table below.

| Unit | Relative to |
| :--- | :--- |
| em | Font size of the parent, in the case of typographical properties like font-size, and font size of the element itself, in the case of other properties like width. |
| rem | Font size of the root element |
| lh | Line height of the element |
| vw | 1% of the viewport width |
| vh | 1% of the viewport height |
| vmin | 1% of the viewport smaller dimension |
| vmax | 1% of the viewport larger dimension |

