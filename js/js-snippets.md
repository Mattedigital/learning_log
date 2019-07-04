# JS Snippets

**Strip HTML tags in Javascript:**

src: [https://css-tricks.com/snippets/javascript/strip-html-tags-in-javascript/](https://css-tricks.com/snippets/javascript/strip-html-tags-in-javascript/)

```javascript
 const StrippedString = OriginalString.replace(/(<([^>]+)>)/ig,"");
```

**See if element has a specific class:**

```javascript
element.classList.contains(class);
```

**Change CSS Variables value:**

```javascript
document.documentElement.style.setProperty('--variableName', newValue);
```

**Get all data attributes on a specific element:**

```javascript
//<div data-text="hello" data-lang="English" data-greeting="true">Hello</div>
const item = document.querySelector('div');
item.dataset // {text: "hello", lang: "English", greeting: "true"}
item.dataset.lang // English
```

**Getting times & dates:**

```javascript
const now = new Date();
const seconds = now.getSeconds();
const minutes = now.getMinutes();
const hours = now.getHours();
```

**bind\(\), apply\(\), call\(\):**

Use `.bind()` when you want a function to later be called with a certain context, useful in events.

Use `.call()` or `.apply()` when you want to invoke the function immediately, and modify the context.

`call` attaches `this` into function and executes the function immediately:

```javascript
var person = {  
  name: "James Smith",
  hello: function(thing) {
    console.log(this.name + " says hello " + thing);
  }
}

person.hello("world");  // output: "James Smith says hello world"
person.hello.call({ name: "Jim Smith" }, "world"); // output: "Jim Smith says hello world"
```

`bind` ****attaches `this`\_ ****\_into function and it needs to be invoked separately like this:

```javascript
var person = {  
  name: "James Smith",
  hello: function(thing) {
    console.log(this.name + " says hello " + thing);
  }
}

person.hello("world");  // output: "James Smith says hello world"
var helloFunc = person.hello.bind({ name: "Jim Smith" });
helloFunc("world");  // output: Jim Smith says hello world"
```

or like this:

```javascript
...    
var helloFunc = person.hello.bind({ name: "Jim Smith" }, "world");
helloFunc();  // output: Jim Smith says hello world"
```

`apply` ****is similar to `call` ****except that it takes an array-like object instead of listing the arguments out one at a time:

```javascript
function personContainer() {
  var person = {  
     name: "James Smith",
     hello: function() {
       console.log(this.name + " says hello " + arguments[1]);
     }
  }
  person.hello.apply(person, arguments);
}
personContainer("world", "mars"); // output: "James Smith says hello mars", note: arguments[0] = "world" , arguments[1] = "mars"
```

**A note on Arrow Function syntax:**

1. immediately after `=>` implies a `return`

```javascript
const a = (who) => "hello " + who + "!";
```

1. Wrapping multiline function in `()`  implies a return but allows you to break the function across multiple lines. 

```javascript
const b = (who) => (
    "hello " + 
    who + 
    "!"
);
```

1. Wrapping function in `{}` means you have to explicitly state `return` but will allow you to write multiple lines. Typically used when complex code is required with a single returned value at the end of it.

```javascript
const c = (who) => {
  return "hello " + who + "!";
};
```

