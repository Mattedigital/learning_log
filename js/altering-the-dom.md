# Altering the DOM

## Query Selector

Selects single element. If many it will select the 1st element found.

```javascript
document.querySelector(selector);
```

## Query Selector All

Allows you to select multiple elements.

```javascript
document.querySelectorAll(selectors);
```

This will return a NodeList. Use `NodeList.foreach` to access individual elements. In older browsers use `Array.from` to convert it to an Array.

## Adding event listeners

```javascript
let thing = document.querySelector('.thing')
thing.addEventListener(event, callback)
```

`callback` is a function that does what ever you want whenever the event is triggered. See example below.

```javascript
thing.addEventListener('click', callback)

function callback (e) {
  e.preventDefault() // Prevents default behavior. Only use this when necessary
  console.log('thing is clicked!')
}
```

### [List of common event types](https://developer.mozilla.org/en-US/docs/Web/Events)

## Removing event listeners

```javascript
thing.addEventListener('click', callback)

function callback () {
  console.log('thing is clicked!')
  // removes event listener
  thing.removeEventListener('click', callback)
}
```

When you remove an event listener you no longer listen to the event. Int he above code the callback only triggers when `.thing` gets clicked for the 1st time. Further clicks will not trigger the callback. To free up resources always remove listeners when you have no further need for them.

## Adding & removing classes

Add a class

```javascript
element.classList.add('classname')
```

Remove a class

```javascript
element.classList.remove('classname')
```

Check if class exists

```javascript
element.classList.contains('classname')
```

## Adding, changing & removing attributes

Get an attribute

```javascript
element.getAttribute('attribute-name')
```

Change / Set an attribute

```javascript
element.getAttribute('attribute-name', 'attribute-value')
```

Remove an attribute

```javascript
removeAttribute('attribute-name')
```

## Adding elements to the DOM

Create an element

```javascript
let li = document.createElement('li')
```

Add content to this new element

```javascript
li.innerHTML = 'Hello again, world!'
```

Add element to the DOM

```javascript
let ul = document.querySelector('ul')
ul.append(li)
```

## Removing elements from the DOM

General example \(can't do this as no way of clarifying which child is being removed\)

```javascript
let parent = document.querySelector('.parent')
let elToRemove = document.querySelector('.element-to-remove')
parent.removeChild(elToRemove)
```

Example of removing 1st child

```javascript
let list = document.querySelector('ul')
removeFirst.addEventListener('click', e => {
  if (list.children.length) {
    let firstNode = list.children[0]
    list.removeChild(firstNode)
  }
})
```

