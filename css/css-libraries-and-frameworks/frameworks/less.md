# LESS

![](../../../.gitbook/assets/unnamed.png)

Less \(Leaner Style Sheets\) is a reverse-compatible language extension or preprocessor for the stylesheet language CSS. This means that any CSS code is also automatically a valid Less code \(but this is not true in the other direction\). The purpose of Less is to make writing CSS code more efficient.

The variables in LESS are declared with the `@` key carachter.

```css
@color-base: #245DE2;

.class1 {
    background-color: @color-base;
}
```

We can also add mixins that are like small functions that we can reuse in the resto of the project.

```css
.gradients {
  background: #eaeaea; 
  background: linear-gradient(top, #eaeaea, #cccccc);
  background: -o-linear-gradient(top, #eaeaea, #cccccc); 
  background: -ms-linear-gradient(top, #eaeaea, #cccccc); 
  background: -moz-linear-gradient(top, #eaeaea, #cccccc); 
  background: -webkit-linear-gradient(top, #eaeaea, #cccccc); 
}

div {
  .gradients;
  border: 1px solid #555;
  border-radius: 3px;
}
```

We can use the LESS elements it's a library with already defined mixins, that we can use. We need to import them with the `@import "elements.less";`

```css
@import "elements.less";

.div {
    .rounded(3px);
}   
```

Nesting the declarations saves us space and improves readability of the code.

```css
nav {
  height: 40px;
  width: 100%;
  background: #455868;
  border-bottom: 2px solid #283744;
  li {
    width: 600px;
    height: 40px;
    a {
      color: #fff;
      line-height: 40px;
      text-shadow: 1px 1px 0px #283744;
    }
  }
}
```

We can make operations in the LESS properties as we can do in plain CSS.

As LESS is a programming language we have a scope variable, that means the value of a variable will not be available everywhere or even change the value depending where it's called.

```css
header {
  @color: black;
  background-color: @color;
  nav {
      @color: blue;
      background-color: @color;
      a {
        color: @color;
      }
  }
}
```

First the `@color` is _black_ for the header itself, but when we enter in the _nav_, the `@color` value now it's changed to _blue_, and it will last for the _nav_ and the _a_.

