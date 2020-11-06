# FlexBox

```css
display: <flex>;
```

`flex` changes an element to a block-level container with flex items inside of it. `inline-flex` allows multiple flex containers to appear inline with each other.

![Axis in FlexBox](../../.gitbook/assets/axes.png)

```css
justify-content: <space-between>;
```

Defines how the browser distributes space between and around content items along the main-axis of a flex container. Can take `flex-start`,`center`,`flex-end`, `space-around`,`space-between`or`space-evenly`or `stretch`.



```css
align-items: <baseline>;
```

Defines how the browser distributes space between and around content items along the cross-axis of a flex container. Can take `flex-start`,`flex-end` ,`center`,`baseline`. If the property is set to `flex-wrap; no-wrap;`



```css
flex-grow: <2>;
```

Sets the flex grow factor if the sum of all the flex items is bigger than the height of the container.



```css
flex-shrink: <3>;
```

Set the flow shrink factor if the sum of all the flex items is bigger than the width container.



```css
flex-basis: <auto>;
```

The initial width of an flex item. Can take `auto` or numerical values.



```css
flex: <2 3 550px>;
```

Shorthand for `flex-grow`, `flex-shrink`, `flex-basis`.



```css
align-content: <flex-start>;
```

The property sets the distribution of space between and around content items along a flexbox's cross-axis. Can take `flex-start`,`flex-end` ,`center`,`baseline`. If the property is set to `flex-wrap; wrap;`



```css
flex-direction: <column-reverse>;
```

Te `flex-direction` CSS property sets how flex items are placed in the flex container defining the main axis and the direction \(normal or reversed\). Can take the `row`,`column`,`row-reverse`,`column-reverse`.



```css
flex-wrap: <wrap-reverse>;
```

Sets whether flex items are forced onto one line or can wrap onto multiple lines. If wrapping is allowed, it sets the direction that lines are stacked, can take `wrap`,`wrap-reverse`,`no-wrap`.



```css
flex-flow: <row> <no-wrap>;
```

Shorthand for `flex-direction` and `flex-wrap`.

