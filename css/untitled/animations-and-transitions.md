# Animations and Transitions

## Animations



## Transitions

CSS transitions allows you to change property values smoothly, over a given duration.

![This is purely made with CSS](../../.gitbook/assets/peek-2021-02-17-10-48.gif)

In order to create a transition, we need to specify two parameters:

* The CSS property you want to add the effect to.
* The duration of the effect.

{% tabs %}
{% tab title="HTML" %}
```markup
<html>
<body>

<h1>The transition Property</h1>

<p>Hover over the div element below, to see the transition effect:</p>
<div></div>
</body>
</html>
```
{% endtab %}

{% tab title="CSS" %}
```css
div {
  width: 100px;
  height: 100px;
  background: red;
  transition: width 2s;
}

div:hover {
  width: 300px;
}
```
{% endtab %}
{% endtabs %}

![](../../.gitbook/assets/transition1.gif)

Also can even change various propery values at a time

{% tabs %}
{% tab title="HTML" %}
```markup

<h1>The transition Property</h1>

<p>Hover over the div element below, to see the transition effect:</p>
<div></div>
</body>
</html>
```
{% endtab %}

{% tab title="CSS" %}
```css
div {
  width: 100px;
  height: 100px;
  background: red;
  transition: width 2s, height 4s;
}

div:hover {
  width: 300px;
  height: 300px;
}
```
{% endtab %}
{% endtabs %}

![](../../.gitbook/assets/transition2.gif)

With `transition-timing-function` we can specify the speed of the curve of the transition effect.

We can specify the following values:

* `ease` - specifies a transition effect with a slow start, then fast, then end slowly \(this is default\)
* `linear` - specifies a transition effect with the same speed from start to end
* `ease-in` - specifies a transition effect with a slow start
* `ease-out` - specifies a transition effect with a slow end
* `ease-in-out` - specifies a transition effect with a slow start and end
* `cubic-bezier(n,n,n,n)` - lets you define your own values in a cubic-bezier function

{% tabs %}
{% tab title="HTML" %}
```markup
<html>
<body>

<h1>The transition-timing-function Property</h1>

<p>Hover over the div elements below, to see the different speed curves:</p>

<div id="div1">linear</div><br>
<div id="div2">ease</div><br>
<div id="div3">ease-in</div><br>
<div id="div4">ease-out</div><br>
<div id="div5">ease-in-out</div><br>


</body>
</html>
```
{% endtab %}

{% tab title="CSS" %}
```css
div {
  width: 100px;
  height: 100px;
  background: red;
  transition: width 2s;
}

#div1 {transition-timing-function: linear;}
#div2 {transition-timing-function: ease;}
#div3 {transition-timing-function: ease-in;}
#div4 {transition-timing-function: ease-out;}
#div5 {transition-timing-function: ease-in-out;}

div:hover {
  width: 300px;
}
```
{% endtab %}
{% endtabs %}

![](../../.gitbook/assets/transition3.gif)

We can even add a delay for the transition

{% tabs %}
{% tab title="HTML" %}
```markup
<html>
<body>

<h1>The transition-delay Property</h1>

<p>Hover over the div element below, to see the transition effect:</p>

<div></div>

<p><b>Note:</b> The transition effect has a 1 second delay before starting.</p>


</body>
</html>

```
{% endtab %}

{% tab title="CSS" %}
```css
div {
  width: 100px;
  height: 100px;
  background: red;
  transition: width 3s;
  transition-delay: 1s;
}

div:hover {
  width: 300px;
}
```
{% endtab %}
{% endtabs %}

![](../../.gitbook/assets/transition4.gif)

We have the shorthand `transition`to specify all the parameters, with just one word. We need to put `transition: transition-property, transition-duration, transition-timing-function, transition-delay`

```css
div {
  transition-property: width;
  transition-duration: 2s;
  transition-timing-function: linear;
  transition-delay: 1s;
}

/* The same as */

div {
transition: width, 2s, linear, 1s;
}
```

