# CSS Specifity

Specifity is the means by which browsers decides which CSS Property are the most relevant and therefore to be aplied. 

The browser decides which property is the most relevant by the weight of this selector. This is the list of the relevancy of selectors

1. Inline styles `<style color:"red">Hello</style>`
2. ID Selectors `<p id="greeting>Hello</p> #p{color:red;}`
3. Class selectors `<p class="greeting">Hello</p> .p{color:red;}`
4. Type selectors `<p>Hello</p> p{color:red;}`

Each selector overrides the anterior, but thats not the way, CSS has a 4 values to calculate specifity, and the union of this can overrides a bigger selector:

The scoring is the next:

1. Inlinye styles =&gt; 1000
2. ID selectors =&gt; 100
3. Class selectors =&gt; 10
4. Type selectors =&gt; 1

{% tabs %}
{% tab title="HTML" %}
```markup
<h1 class="greetingClass" id="greetingId">Hello</h1>
```

```css
h1{
    color:red;  /*Score 1 */
}

.greetingClass {
    color:blue;    /* Score 10 */
}

#greetingId {
    color:yellow;    /* Score 100 */
}

In this case the color will be Yellow.
```

```css
h1.greetingClass{
    color:red;  /*Score 11 */
}

.greetingClass {
    color:red;    /* Score 10 */
}

#greetingId {
    color:yellow;    /* Score 100 */
}

In this case the color will still be Yellow.
```

```css
h1.greetingClass{
    color:red;  /*Score 11 */
}

.greetingClass#greetingId  {
    color:blue;    /* Score 110*/
}

#greetingID {
    color:yellow;    /* Score 100 */
}

In this case the color will be blue, because the score is greater
than the ID selector.
```

```css
h1.greetingClass#greetingID{
    color:red;  /*Score 111 */
}

.greetingClass#greetingId  {
    color:blue;    /* Score 110*/
}

#greetingID {
    color:yellow;    /* Score 100 */
}

And finally this case will be red.
```
{% endtab %}
{% endtabs %}

