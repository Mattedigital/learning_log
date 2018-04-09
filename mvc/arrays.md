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

You can also pass a initial value as a callback:

```js
[0, 1, 2, 3, 4].reduce( (accumulator, currentValue) => {
    accumulator + currentValue 
}, 10);
//returns 20 as it starts from 10.
```

##### Filter:

The `filter` method is used to iterate through an array and filter out elements where a given condition is not true. Any array element for which the callback returns true will be kept and elements that return false will be filtered out.

```js
const newArray = array.filter(val => val !== 5);
```

##### Sort:

You can use the method `sort` to easily sort the values in an array alphabetically or numerically. Unlike the previous array methods we have been looking at, `sort` actually alters the array in place.

```js
const newArray = array.sort((a, b) => a - b);
```

This works by iterating through the array taking a & b, if a - b is &lt; 0 then a goes before b. If a - b is &gt; 0 then b goes before a. If a - b is 0 then no difference and leave as is. The `sort` function then continues with the new a, b values.

##### Reverse:

You can use the `reverse` method to reverse the elements of an array.

```js
const myArr = [1, 2, 3, 4];
myArr.reverse()
//returns [4, 3, 2, 1]
```

##### Concat:

`concat` can be used to merge the contents of two arrays into one. `concat` takes an array as an argument and returns a new array with the elements of this array concatenated onto the end.

```js
const oldArray = [1, 2, 3];
const newArray = oldArray.concat([4, 5, 6]);
```

& in es6 using the spread operator:

```js
const newArray = [...oldArray, 4, 5, 6];
```

##### Split:

Use the split method to split a string into an array. The value you pass the split method will be the split point. Here is an example using whitespace as the split point:

```js
const str = "Hello World";
const strArr = str.split(' ');
```

##### Join:

Use the `join` method to join each element of an array into a string separated by whatever delimiter you provide as an argument:

```js
const veggies = ['Celery', 'Radish', 'Carrot', 'Potato'];
const salad = veggies.join(' and ');
// salad = 'Celery and Radish and Carrot and Potato'
```



