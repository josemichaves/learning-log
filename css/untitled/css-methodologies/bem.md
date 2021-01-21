# BEM

BEM stands for Block Element Modifier. 

This methodology only usses the classes, not id or tags.

As the name suggest it focus in these three entities:

## Block

Any element of the DOM can be a block, usually the block is the wrapper. The naming can contain letters, digits and dashes.

{% tabs %}
{% tab title="Block" %}
```markup
<div class="block">
    ...
</div>
```

```css
.block {
    color: red;
}
```
{% endtab %}
{% endtabs %}

## Element

If a standalone has no standalone meaning, then it's an element. The css naming is formed by the element name which are children, plus two underscores and the element itselfs name

{% tabs %}
{% tab title="Block" %}
```markup
<div class="block block__element">
    ...
</div>
```

```css
.block__element {
    color: red;
}
```
{% endtab %}
{% endtabs %}

## Modifier

If this entitiy modifies the apparence, state or behaviour then it's a modifier. The naming is made by the element or block name plus two dashes.

{% tabs %}
{% tab title="Block" %}
```markup
<div class="block block__element block__element--modifier">
    ...
</div>
```

```css
.block__element--modifier {
    color: red;
}
```
{% endtab %}
{% endtabs %}

## Example

{% tabs %}
{% tab title="Block" %}
```markup
<form class="form form--theme-xmas form--simple">
  <input class="form__input" type="text" />
  <input
    class="form__submit form__submit--disabled"
    type="submit" />
</form>
```

```css
.form { }
.form--theme-xmas { }
.form--simple { }
.form__input { }
.form__submit { }
.form__submit--disabled { }
```
{% endtab %}
{% endtabs %}

