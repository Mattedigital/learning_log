**Strip HTML tags in Javascript:**

src: [https://css-tricks.com/snippets/javascript/strip-html-tags-in-javascript/](https://css-tricks.com/snippets/javascript/strip-html-tags-in-javascript/)

```js
 const StrippedString = OriginalString.replace(/(<([^>]+)>)/ig,"");
```

**See if element has a specific class:**

```js
element.classList.contains(class);
```

**Change CSS Variables value:**

```js
document.documentElement.style.setProperty('--variableName', newValue);
```

**Get all data attributes on a specific element:**

```js
//<div data-text="hello" data-lang="English" data-greeting="true">Hello</div>
const item = document.querySelector('div');
item.dataset // {text: "hello", lang: "English", greeting: "true"}
item.dataset.lang // English
```



