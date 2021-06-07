# Event bubbling

When an event happens on an element, it first runs the handlers on it, then on its parent, then all the way up on other ancestors.

That means that if we click in the child of a div, the code will run both in the child and the parent.

![This a schema to understand event bubbling.](../../.gitbook/assets/image%20%2836%29.png)

Here is it the code example for it.

```markup
<form action="" onclick="alert('I\'m the FORM')">
		FORM
    
	<div onclick="alert('I\'m the DIV')">DIV
			
		<p onclick="alert('I\'m the P')">P</p>
	</div>
</form>
```

We can see that this elements are nested inside each other, and everyone have a `onclick` to tell where we've clicked. The strange happens if we click in the `P` element, we'll have 3 alerts, one for the `P`, one for the `div`, and other for the `form`, and if we click in the `div`, we only will have two the `div` and the `form`.

Why is this happening? That's the way the DOM works, first run the handlers in the deepest levels and then continue the execution to the outers levels. 

To stop this execution we can call the `stopPropagation()`

```markup
<form action="" onclick="alert('I\'m the FORM')">
		FORM
    
	<div onclick="alert('I\'m the DIV')">DIV
			
		<p onclick="alert('I\'m the P')">P</p>
		<button onclick="event.stopPropagation()"> Click to stop propagation </button>
	</div>
</form>
```

Now if we click the button and then click the `P` will only show the alert for the `P` .



