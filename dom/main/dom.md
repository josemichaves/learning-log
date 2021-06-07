# Whats is the DOM?

The Document Object Model \(DOM\) is a programming interface for HTML and XML documents. It represents the page so that programs can change the document structure, style, and content. The DOM represents the document as nodes and objects. That way, programming languages can connect to the page.

The DOM model is represented as a tree of objects

![](../../.gitbook/assets/pic_htmltree.gif)

The way that we have to acces to the DOM is via the **document** object it represents the tree of the DOM structure, inside of the **document** object exist two properties **element** and **node:**

* **element:** this are the HTML tag \(div, span, h1, input, etc\)
* **node:** is an more basic unity, it can be an element or a text node

First of all we need to insert the Javascript in to the html.

```markup
<head>
    <script>
        document.getElementById('demo').innerHTML = "Hello World"
    </script>
</head>

// or

<body>
    <script> /* It needs to be at the end of the body */
        document.getElementById('demo').innerHTML = "Hello World"
    </script>
</body>

// or external js 

<head>
    <script src="myJs.js"> </script>
</head>

// or

<body>
    <script src="myJs.js"> /* It needs to be at the end of the body */ </script>
</body>

```

We can select the elements in the DOM:

```javascript
document.getElementById('idOfElement') //returns the element or null
document.getElementsByClassName('classOfElement') //returns the element or []
document.getElementsByName('nameOfElement') //returns the element or []
document.getElementsByTagName('htmlTagName') //returns the element or []
```

This was the traditional way to do it, we also have two modern ways to select elements

```javascript
//Search the first element that have the css selector specified or return null
document.querySelector('selector') 

//Search all the elements that have this css selector or return []
document.querySelectorAll('selector')
```

We can even create elements inside the HTML via the Javascript and the DOM

```javascript
document.createElement('htmlTag') //It creates this tag
document.createComment('Comment') //Creates a comment inside the HTML code
document.createTextNode('textToAdd') //Creates a node of text
```

We also can specify attributes when we're using the `.createElement` 

```javascript
const div = document.createElement('div') //creates the <div></div>
div.id = 'page' // <div id="page"> </div>
div.className = 'data' // <div id="page" class="data"> </div>
div.style = 'color: red' //<div id="page" class="data" style="color:red"> </div>
```

One of the most used methods is the `appendChild()` it let us to insert something as children of an element.

```javascript
const img = document.createElement("img");
img.src = "img/js-logo.jpg";
img.alt = "Javascript Logo";

document.body.appendChild(img);
```

Here we're inserting this image as child of the body



