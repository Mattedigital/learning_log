#### Arrays

##### Map:

The `map` method is a convenient way to iterate through arrays.

```js
const oldArray = [1, 2, 3];
const timesFour = oldArray.map(val => val * 4);
console.log(timesFour); // returns [4, 8, 12]
console.log(oldArray);  // returns [1, 2, 3]
```

##### Reduce:

The array method `reduce` is used to iterate through an array and condense it into one value.

```js
[0, 1, 2, 3, 4].reduce(
  function (
    accumulator,
    currentValue,
    currentIndex,
    array
  ) {
    return accumulator + currentValue;
  }
);

// returns 10
```

The above can be abbreviated to:

```js
[0, 1, 2, 3, 4].reduce( (accumulator, currentValue) => accumulator + currentValue );
// returns 10, same as above.
```

You can also pass a starting point as a callback:

```js
[0, 1, 2, 3, 4].reduce( (accumulator, currentValue) => {
    accumulator + currentValue 
    }, 10
);
//returns 20 as it starts from 10.
```

##### Filter:

The `filter` method is used to iterate through an array and filter out elements where a given condition is not true. Any array element for which the callback returns true will be kept and elements that return false will be filtered out.

```js
array.filter(val => val !== 5);
```



