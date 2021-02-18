# SASS

![](../../../.gitbook/assets/256px-sass_logo_color.svg.png)

Sass is a CSS preprocessor, which adds special features such as variables, nested rules and mixins \(sometimes referred to as syntactic sugar\) into regular CSS. The aim is to make the coding process simpler and more efficient.

In Sass we have two syntax options:

* SCSS: Use the CSS syntax and it's fully compilant with CSS syntax, uses the .scss extension.
* SASS: Uses the indentation rather than brackets, it's not fully compilant with CSS.

{% tabs %}
{% tab title="SCSS" %}
```css
.button {
    background: cornflowerblue;
    border-radius: 5px;
    padding: 10px 20px;
    
    &:hover{
        cursor: pointer;
    }
    
    &:disabled{
        cursor: default;
        background: grey;
    }
}
```
{% endtab %}

{% tab title="SASS" %}
```css
.button 
    background: cornflowerblue;
    border-radius: 5px;
    padding: 10px 20px;
    
    &:hover
        cursor: pointer;
    
    &:disabled
        cursor: default;
        background: grey;
```
{% endtab %}
{% endtabs %}

As we can see in SASS we can nest elements, and it means, everything inside the button will be affected with this parameters.

We can store variables, that we can reuse later. With the `$` we declare de variable, and when we call the variable we call it with the `$` also.

```css
$font-stack:    Helvetica, sans-serif;
$primary-color: #333;

body {
  font: 100% $font-stack;
  color: $primary-color;
}

/* This will produce the following CSS */

body {
  font: 100% Helvetica, sans-serif;
  color: #333;
}
```

We can nest elements, but we need to be extremely careful, when doing it, because it can lead in over-qualified CSS if not executed carefully. The best way to nest is to mimic HTML hierarchy.

```css
nav {
  ul {
    margin: 0;
    padding: 0;
    list-style: none;
  }

  li { 
    display: inline-block; 
  }

  a {
    display: block;
    padding: 6px 12px;
    text-decoration: none;
  }
}

/* This will produce the following CSS */

nav ul {
  margin: 0;
  padding: 0;
  list-style: none;
}

nav li {
  display: inline-block;
}

nav a {
  display: block;
  padding: 6px 12px;
  text-decoration: none;
}

```

The mixins are a great way to convert long and repetitive properties in a single property, it's like a function that you can call and reuse with the values you need.

```css
@mixin border-radius($radius) {
  -webkit-border-radius: $radius;
     -moz-border-radius: $radius;
      -ms-border-radius: $radius;
          border-radius: $radius;
}

.box { 
  @include border-radius(10px); 
}

/* The following is produced */
.box {
  -webkit-border-radius: 10px;
  -moz-border-radius: 10px;
  -ms-border-radius: 10px;
  border-radius: 10px;
}
```

We declare the mixin with `@mixin` and then the naming of the function that we want, later within the parenthesis we specify the parameter we'll be recieving, and inside the curly-braces the properties that will affect the mixin. When we call the mixin inside a new property we call the `@include` followed by the name and parameter of the mixin.

The extend allows us to reuse or properties in another property.

```css
.error {
  border: 1px #f00;
  background-color: #fdd;

  &--serious {
    @extend .error;
    border-width: 3px;
  }
}

/* It produces */
.error, .error--serious {
  border: 1px #f00;
  background-color: #fdd;
}
.error--serious {
  border-width: 3px;
}
```

We can also use the operators in SASS, we can use the default operators to calculate values of the properties

```css
nav {
  ul {
    margin: 0 + 2;
    padding: (10 / 2);
    list-style: none;
  }

  li { 
    display: inline-block; 
  }

  a {
    display: block;
    padding: 6 * 2;
    text-decoration: none;
  }
}

/* The following is produced */

nav ul {
  margin: 2;
  padding: 5;
  list-style: none;
}

nav li {
  display: inline-block;
}

nav a {
  display: block;
  padding: 12;
  text-decoration: none;
}
```

Note that for the division we need to wrap it in parenthesis because the `/`is a reserved character of CSS.

We cannot make the operators work with different units, for example we cannot do `2px + 3rem`

