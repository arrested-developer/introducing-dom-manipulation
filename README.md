# introducing-dom-manipulation
An intro to DOM manipulation with vanilla JS

## Tutorial

### Step 1 - The DOM

Open the index.html page from this repo, you can find it [here](https://arrested-developer.github.io/introducing-dom-manipulation/)

Open the dev tools Javascript console in your browser -- In Chrome you can press Command+Option+J (Mac) or Control+Shift+J (PC)

First, type into your console

```
console.log(document)
```

What you see here is a representation of the DOM - the **D**ocument **O**bject **M**odel

If we type 

```
typeof document
```

We should see that it is an object. The DOM is how Javascript interacts with a web page, using a Javascript object that represents the structure of the HTML page.

### Step 2 - Selecting elements

If you look at the HTML source of the page, you'll see that each shape is a `section` with its own unique id.

We can select these elements of the page in a few different ways:

`document.getElementById('square')` should get you the square section. It returns just one element (every element _should_ have a unique ID, so there should only ever be one thing to return)

`document.querySelector('#square')` will also get you the square section. querySelector takes any CSS selector and queries the contents of the DOM. It returns **one** result.

`document.querySelectorAll('.red')` will get you _both_ the elements with the class `red`. They will come back as an array.

* How would you select the section with the id of circle?
* What is returned by `document.querySelectorAll('#square')` ?
* What is returned by `document.querySelector('.red')` ?

### Step 3 - Changing text content

Although they appear in the Chrome console as HTML elements, DOM nodes are Javascript objects, with many properties and methods.

The `innerText` property contains whatever text is inside the element.

We can use `document.getElementById('square').innerText` to get the text inside of the square.
To change it, we just use `=` to assign a new value
`document.getElementById('square').innerText = 'I love right angles'` will change the text inside the element on the page. Take a look! 👀

* How could you change the text inside the triangle?

### Step 4 - Adding and removing classes

Let's start by assigning the circle to a variable
`var circle = document.querySelector('#circle')`

Now we can use methods on the object `circle` to add and remove classes.

To remove the `blue` class from the section, we can write:
`circle.removeClass('blue')`

Take a peek and see how it looks.

To add the yellow class, we can write:
`circle.addClass('yellow')`

* What now would be returned by `document.querySelectorAll('yellow')` ?
* How would you change the rectangle to appear blue by adding and removing classes?

## Step 5 - Add event listeners

To further embed the fun of Javascript interactivity into the DOM, we can add event listeners to elements. There are many different events you can listen for, but some of the most often used are `click`, `onmouseover`, `onload`. They all happen at different times, you can read more [here](https://www.w3schools.com/js/js_htmldom_eventlistener.asp)

We're going to add a click event listener to the rectangle.

Start by creating a variable to store the rectangle DOM node

We're going to make a new function that changes the class of the target that is clicked on:

```
function changeClass(event) {
event.target.classList.toggle('bigBorders');
}
```

Now we're going to add our new function to an event listener by typing:

`rectangle.addEventListener('click', changeClass)`

## Step 6 - Directly changing CSS properties

[CSS properties in Javascript](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Properties_Reference) are often written slightly differently than in CSS.

Have a read through the above link, then try to target specific elements in the DOM and change their properties. Get creative! 🎨

## More Resources

+ [Google: 'Get Started with DevTools console'](https://developers.google.com/web/tools/chrome-devtools/console/get-started)
+ [Google: 'DevTools for Beginners - the DOM'](https://developers.google.com/web/tools/chrome-devtools/beginners/html)
+ [Call Me Nick - DOM Manipulation Basics](https://web.archive.org/web/20170718105716/https://callmenick.com/post/basics-javascript-dom-manipulation) (archived version) will cover a lot of the basics.
+ [MDN article on "Manipulating Documents"](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Client-side_web_APIs/Manipulating_documents) - useful for some further reading, if you'd like
+ [Appspot's DOM Tutorials: Exercises 1,2 & 3 only](https://dom-tutorials.appspot.com/static/index.html) will help put that into practice.
+ Bonus videos:
  + [Live coding intro to the DOM, with JS examples](https://www.youtube.com/watch?v=eaLKqoB9Fu0)

