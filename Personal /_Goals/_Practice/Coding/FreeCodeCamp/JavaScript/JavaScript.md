#Practice 
#Coding
#FreeCodeCamp 
#JavaScript 

---
# Recursion

Recursion is the concept that a function can be expressed in terms of itself.

```javascript
function sum(arr, n) {
  // Only change code below this line
  if (n <= 0) {
       
        return 0;

    } else {
        
        return sum(arr, n - 1) + arr[n - 1];

    }
  // Only change code above this line
}
```

## Example

```js
function sum([2, 3, 4], 1) {
  // Only change code below this line
  if (1 <= 0) {
       
        return 0;

    } else {
        
        return sum([2, 3, 4], 0) + arr[0]; --> Returns 2

    }
  // Only change code above this line
}

function sum([2, 3, 4], 0) {
  // Only change code below this line
  if (1 <= 0) {
       
        return 0;

    } else {
        
        return sum([2, 3, 4], 0) + arr[0];

    }
  // Only change code above this line
}

Returns 2


```

```js
function sum([2, 3, 4, 5], 3) {
  // Only change code below this line
  if (n <= 0) {
       
        return 0;

    } else {
        
        return sum([2, 3, 4, 5], 2)* + arr[2]; --> returns +4

    }
  // Only change code above this line
}


*function sum([2, 3, 4, 5], 2) {
  // Only change code below this line
  if (n <= 0) {
       
        return 0;

    } else {
        
        return sum([2, 3, 4, 5], 1)** + arr[1]; --> +3

    }
  // Only change code above this line
}


**function sum([2, 3, 4, 5], 1) {
  // Only change code below this line
  if (n <= 0) {
       
        return 0;

    } else {
        
        return sum([2, 3, 4, 5], 0) + arr[0]; +2

    }
  // Only change code above this line
}

return 9 <--(4 + 3 + 2)
```

# Profile Lookup

In dieser Aufgabe musste man beachten, dass die Funktion nach "return" abschließt.
Wenn also der Loop kein return-Wert ausgibt, kommt eben der return "No contacts found".

Vorherige versuche waren mit dem While loop.

```js
// Setup

const contacts = [

  {

    firstName: "Akira",

    lastName: "Laine",

    number: "0543236543",

    likes: ["Pizza", "Coding", "Brownie Points"],

  },

  {

    firstName: "Harry",

    lastName: "Potter",

    number: "0994372684",

    likes: ["Hogwarts", "Magic", "Hagrid"],

  },

  {

    firstName: "Sherlock",

    lastName: "Holmes",

    number: "0487345643",

    likes: ["Intriguing Cases", "Violin"],

  },

  {

    firstName: "Kristian",

    lastName: "Vos",

    number: "unknown",

    likes: ["JavaScript", "Gaming", "Foxes"],

  },

];

  

function lookUpProfile(name, prop) {

  // Only change code below this line

  

  for (var i = 0; i < contacts.length; i++) {

  

    if (contacts[i].firstName == name) {

  

      if (contacts[i].hasOwnProperty(prop)) {

  

        return contacts[i][prop];

      } else {

        return "No such property";

      }

    }

  }

  return "No such contact";

  // Only change code above this line

}

  

lookUpProfile("Akira", "likes");
```

# Random Whole Numbers

```js
Math.floor(Math.random() * (max - min + 1)) + min

Math.floor(Math.random() * (10 - 5 + 1)) + 5

Math.floor(Math.random() * (6)) + 5
```

# Conditional Operator
Alternative yu if-Statemants

```js
function findGreater(a, b) {
  if(a > b) {
    return "a is greater";
  }
  else {
    return "b is greater or equal";
  }
}
```

```js
function findGreater(a, b) {
  return a > b ? "a is greater" : "b is greater or equal";
}
```

# Recursion
```js
function countup(n) {
  if (n < 1) {
    return [];
  } else {
    const countArray = countup(n - 1);
    countArray.push(n);
    return countArray;
  }
}
console.log(countup(5));

```
The value [1, 2, 3, 4, 5] will be displayed in the console.

## Recursion to create a Range of Numbers
```js
function rangeOfNumbers(startNum, endNum) {

  if(startNum > endNum) {

    return [];

  } else {

    const countArray = rangeOfNumbers(startNum, endNum - 1);

    countArray.push(endNum);

    return countArray;

  }

}

```