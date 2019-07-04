# Functional Programming

[https://codewords.recurse.com/issues/one/an-introduction-to-functional-programming](https://codewords.recurse.com/issues/one/an-introduction-to-functional-programming)

Use Pure functions.

Do not create side-effects. Side effects consist of anything that is not a functions returned value, an example can be a stray console.log or changing the value of a variable outside of the function scope.

You should always clone arrays and objects and then alter the

Do not Iterate. Instead Recurse. \(recursive function is a function that calls itself \(look into this - mindset\)\)

Do not Loop. Use map, reduce, filter.

Iteration example: BAD

```javascript
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

```javascript
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

Use [Higher Order Functions](../overview/terminology.md):

```javascript
function makeAdjectifier(adjective) {
    return function (noun) {
        return `${adjective} ${noun}`;
    };
}

const holify = makeAdjectifier('holy');
holify('JS'); // 'holy JS'
holify('cow'); // 'holy cow'
```

HOF benefits =

Composition: Allows us to put lots of small functions within larger functions.

**Closures:**

[https://medium.com/dailyjs/i-never-understood-javascript-closures-9663703368e8](https://medium.com/dailyjs/i-never-understood-javascript-closures-9663703368e8)

[https://medium.com/written-in-code/practical-uses-for-closures-c65640ae7304](https://medium.com/written-in-code/practical-uses-for-closures-c65640ae7304)

[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures)

Sometimes closures show up when you don’t even notice it. You may have seen an example of what we call partial application. Like in the following code.

in es6:

```javascript
let c = 4
const addX = x => n => n + x
const addThree = addX(3)
let d = addThree(c)
console.log('example partial application', d)
```

In case the arrow function throws you off, here is the equivalent.

```javascript
let c = 4
function addX(x) {
  return function(n) {
     return n + x
  }
}
const addThree = addX(3)
let d = addThree(c)
console.log('example partial application', d)
```

We declare a generic adder function`addX`that takes one parameter \(`x`\) and returns another function.

The returned function also takes one parameter and adds it to the variable`x`.

The variable`x`is part of the closure. When the variable`addThree`gets declared in the local context, it is assigned a function definition and a closure. The closure contains the variable`x`.

So now when`addThree`is called and executed, it has access to the variable`x`from its closure and the variable`n`which was passed as an argument and is able to return the sum.

In this example the console will print the number`7`.

**Module Pattern:**

```javascript
var dwightSalary = (function() {
    //private variable
    var salary = 60000;
    //private function (as shown by TypeError at the bottom)
    function changeBy(amount) {
        salary += amount;
    }
    return {
        //public functions, shown by there use below
        raise: function() {
            changeBy(5000);
        },
        lower: function() {
            changeBy(-5000);
        },
        currentAmount: function() {
            return salary;
        }
    }; 
})();

alert(dwightSalary.currentAmount()); // $60,000
dwightSalary.raise();
alert(dwightSalary.currentAmount()); // $65,000
dwightSalary.lower();
dwightSalary.lower();
alert(dwightSalary.currentAmount()); // $55,000

dwightSalary.changeBy(10000) // TypeError: undefined is not a function
```

