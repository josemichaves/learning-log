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

