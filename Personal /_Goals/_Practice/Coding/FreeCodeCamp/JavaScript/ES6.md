#Practice 
#Coding 
#FreeCodeCamp
#JavaScript 

---

# Create Strings using Template Literals
## From 
```js
const result = {
  success: ["max-length", "no-amd", "prefer-arrow-functions"],
  failure: ["no-var", "var-on-top", "linebreak"],
  skipped: ["no-extra-semi", "no-dup-keys"]

};

function makeList(arr) {
  // Only change code below this line

  const failureItems = [];

  // Only change code above this line
  return failureItems;

}

const failuresList = makeList(result.failure);
```

## To
```js
const result = {
  success: ["max-length", "no-amd", "prefer-arrow-functions"],
  failure: ["no-var", "var-on-top", "linebreak"],
  skipped: ["no-extra-semi", "no-dup-keys"]
};

function makeList(arr) {
  // Only change code below this line
  const failureItems = [];
  for (let i = 0; i < arr.length; i++) {
   failureItems.push(`<li class="text-warning">${result.failure[i]}</li>`);

  }
  // Only change code above this line
  return failureItems;
}
  
const failuresList = makeList(result.failure);
```

# # Use class Syntax to Define a Constructor Function

## Example
```js
// Explicit constructor
class SpaceShuttle {
  constructor(targetPlanet) {
    this.targetPlanet = targetPlanet;
  }
  takeOff() {
    console.log("To " + this.targetPlanet + "!");
  }
}

// Implicit constructor 
class Rocket {
  launch() {
    console.log("To the moon!");
  }
}

const zeus = new SpaceShuttle('Jupiter');
// prints To Jupiter! in console
zeus.takeOff();

const atlas = new Rocket();
// prints To the moon! in console
atlas.launch();
```

## From
```js
// Only change code below this line

// Only change code above this line
const carrot = new Vegetable('carrot');
console.log(carrot.name); // Should display 'carrot'
```

## To
```js
// Only change code below this line

  class Vegetable {
    constructor(name){
      this.name = name;
    }

  }
// Only change code above this line
const carrot = new Vegetable('carrot');
console.log(carrot.name); // Should display 'carrot'
```

# Use getters and setters to Control Access to an Object

## Example
```js
class Book {
  constructor(author) {
    this._author = author;
  }
  // getter
  get writer() {
    return this._author;
  }
  // setter
  set writer(updatedAuthor) {
    this._author = updatedAuthor;
  }
}
const novel = new Book('anonymous');
console.log(novel.writer);
novel.writer = 'newAuthor';
console.log(novel.writer);
```

## From
```js
// Only change code below this line

// Only change code above this line

const thermos = new Thermostat(76); // Setting in Fahrenheit scale
let temp = thermos.temperature; // 24.44 in Celsius
thermos.temperature = 26;
temp = thermos.temperature; // 26 in Celsius
```

## To
```js
// Only change code below this line

class Thermostat {
  constructor(Fahreneinheit) {
    this._fahreneinheit = Fahreneinheit;
    }
  //getter

    get temperature(){

      return 5/9 * (this._fahreneinheit - 32);
    }
    //setter
    set temperature(temperature){
      this._fahreneinheit = temperature * 9 / 5 + 32;
      }
}

// Only change code above this line
const thermos = new Thermostat(76); // Setting in Fahrenheit scale
let temp = thermos.temperature; // 24.44 in Celsius
thermos.temperature = 26;
temp = thermos.temperature; // 26 in Celsius
```
