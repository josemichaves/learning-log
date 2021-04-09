# Pseudo-classes

The pseudo-classes are used to define a special state of an element

Normally they're used like temporararly styles for an element.

They're declared as it follows `selector:pseudoClass`

The most used are: `:hover, :active, :before, :after`

```css
button:hover {
  color: red;
}
```

![](../../.gitbook/assets/peek-2021-04-09-10-34.gif)

```css
button:active {
  color: red;
}
```

![](../../.gitbook/assets/peek-2021-04-09-10-37.gif)

Two importants pseudo selectors are the `:before` and `:after` these properties allow us to introduce content before or after a element, via the CSS could be useful to make a little indicator or something like that.

The `:before` introduces before the element

```css
button:before{
    content: "🔵";
}
```

![](../../.gitbook/assets/screenshot-20210409104028-411x132.png)

The `:after` introduces after the element

```css
button:after{
    content: "🔵";
}
```

![](../../.gitbook/assets/screenshot-20210409104037-307x116.png)

