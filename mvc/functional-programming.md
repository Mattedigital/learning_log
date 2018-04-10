

https://codewords.recurse.com/issues/one/an-introduction-to-functional-programming

Use Pure functions.

Do not create side-effects. Side effects consist of anything that is not a functions returned value, an example can be a stray console.log or changing the value of a variable outside of the function scope.

You should always clone arrays and objects and then alter the

Do not Iterate. Instead Recurse. \(recursive function is a function that calls itself \(look into this - mindset\)\)

Do not Loop. Use map, reduce, filter.

Iteration example: BAD

```js
function sum (numbers) {
    let total = 0;
    for (i = 0; i < numbers.length; i++) {
        total += numbers[i];
    }
    return total;
}
sum([0, 1, 2, 3, 4]); //10
```

This is bad practise as we are changing the value of `i` on each loop, we want such variables to be immutable. 

```js
function sum (numbers) {
    if (numbers.length === 1) {
        return numbers[0];
    } else {
        return numbers[0] + sum(numbers.slice(1));
    }
}
sum([0, 1, 2, 3, 4]); //10
```

This is good practice as no variables are altered.

