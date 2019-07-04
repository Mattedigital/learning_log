# Arrays

## Map:

The `map` method is a convenient way to iterate through arrays.

```javascript
const oldArray = [1, 2, 3];
const timesFour = oldArray.map(val => val * 4);
// timesFour = [4, 8, 12]
```

## Reduce:

The array method `reduce` is used to iterate through an array and condense it into one value.

```javascript
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

```javascript
[0, 1, 2, 3, 4].reduce( (accumulator, currentValue) => accumulator + currentValue );
// returns 10, same as above.
```

You can also pass a initial value as a callback:

```javascript
[0, 1, 2, 3, 4].reduce( (accumulator, currentValue) => {
    accumulator + currentValue 
}, 10);
//returns 20 as it starts from 10.
```

## Filter:

The `filter` method is used to iterate through an array and filter out elements where a given condition is not true. Any array element for which the callback returns true will be kept and elements that return false will be filtered out.

```javascript
const array = [1, 4, 12, 65];
const newArray = array.filter(val => val > 5);
// newArray = [12, 65];
```

## Sort:

You can use the method `sort` to easily sort the values in an array alphabetically or numerically. Unlike the previous array methods we have been looking at, `sort` actually alters the array in place.

```javascript
const array = [7, 3, 29, 98, 2];
const newArray = array.sort((a, b) => a - b);
// newArray = [2, 3, 7, 29, 98];
```

This works by iterating through the array taking a & b, if a - b is &lt; 0 then a goes before b. If a - b is &gt; 0 then b goes before a. If a - b is 0 then no difference and leave as is. The `sort` function then continues with the new a, b values.

## Reverse:

You can use the `reverse` method to reverse the elements of an array.

```javascript
const myArr = [1, 2, 3, 4];
myArr.reverse()
//returns [4, 3, 2, 1]
```

## Concat:

`concat` can be used to merge the contents of two arrays into one. `concat` takes an array as an argument and returns a new array with the elements of this array concatenated onto the end.

```javascript
const oldArray = [1, 2, 3];
const newArray = oldArray.concat([4, 5, 6]);
// newArray = [1, 2, 3, 4, 5, 6];
```

& in es6 using the spread operator:

```javascript
const newArray = [...oldArray, 4, 5, 6];
// newArray = [1, 2, 3, 4, 5, 6];
```

## Split:

Use the split method to split a string into an array. The value you pass the split method will be the split point. Here is an example using whitespace as the split point:

```javascript
const str = "Hello World";
const strArr = str.split(' ');
// strArr = ['Hello', 'World'];
```

## Join:

Use the `join` method to join each element of an array into a string separated by whatever delimiter you provide as an argument:

```javascript
const veggies = ['Celery', 'Radish', 'Carrot', 'Potato'];
const salad = veggies.join(' and ');
// salad = 'Celery and Radish and Carrot and Potato'
```

