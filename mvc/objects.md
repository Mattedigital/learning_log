#### Objects

Create `objects` as a variable:

```js
const bike = {
    seats: 1,
    wheels: 2,
    color: 'red',
}
```

Through `constructor` functions:

```js
const bike = function() {
    this.seats = 1;
    this.wheels = 2;
    this.color = 'red';
}
```

Adding `parameters` to our `constructor`:

```js
const bike = function(seats, wheels, color) {
    this.seats = seats;
    this.wheels = wheels;
    this.color = color;
}

const tricycle = new bike(1, 3, 'blue');
```

To use a `constructor`  function we call it with the `new` keyword in front of it. You can then add to the object as the example shows:

```js
const bike = function() {
    this.seats = 1;
    this.wheels = 2;
    this.color = 'red';
}

const motorBike = new bike();

motorBike.engine = 1;
```

Example of using variables instead of `this` allows us to create private `methods` & `properties`: 

```js
const bike = function() {

  // this is a private variable
  let gear = 1;

  // these are public methods
  this.setGear = function(newGear) {
    gear = newGear;
  };

  this.getGear = function() {
    return gear;
  };

};

const tandem = new bike();
```



