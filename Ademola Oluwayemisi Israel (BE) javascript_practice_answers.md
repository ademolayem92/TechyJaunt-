# ADEMOLA Oluwayemisi Israel(BE)JavaScript Practice Answers

## Variables

### Question 1: Create and print variables
```javascript
var bunny = 'Flopsy';
let dog = 'Rover';
const cat = 'Whiskers';
console.log(bunny, dog, cat);
```

### Question 2: Valid and invalid names
* `1bunny` — invalid (Correction: `bunny1`)
* `_bunny` — valid
* `$bunny` — valid
* `"-bunny"` — invalid (Correction: `bunnyMinus` or `bunny_dash`)
* `@bunny` — invalid (Correction: `bunnyAt`)
* `bunnyName` — valid

### Question 3: Predict output and scope behavior
```javascript
console.log(pet); // Output: undefined (due to var hoisting)
var pet = 'lucy';
console.log(animal); // Output: ReferenceError: Cannot access 'animal' before initialization
let animal = 'tom';
```
`var` declarations are hoisted and initialized with `undefined`, whereas `let` declarations are hoisted but remain in a temporal dead zone until initialization.

### Question 4: Local vs global scope
```javascript
const globalAnimal = 'Elephant';
function printAnimals() {
    const animalName = 'Cat';
    console.log(animalName);
    console.log(globalAnimal);
}
printAnimals();
```

## Data Types

### Question 5: Bunny object properties
```javascript
const bunny = { name: 'Lucy', age: 3, isHappy: true };
console.log(bunny.name);
console.log(bunny.age);
console.log(bunny.isHappy);
```

### Question 6: Types using typeof
```javascript
console.log(3.14, typeof 3.14);
console.log('Lucy', typeof 'Lucy');
console.log(true, typeof true);
console.log(null, typeof null); // object (historical JS quirk)
console.log(undefined, typeof undefined);
console.log(Symbol('Lucy'), typeof Symbol('Lucy'));
console.log({ name: 'Lucy' }, typeof { name: 'Lucy' });
console.log(['Lucy', 'Tom'], typeof ['Lucy', 'Tom']); // object
```

### Question 7: Mixed data types array
```javascript
const mixedDataTypes = [true, 42, 'hello', null, undefined, { key: 'value' }];
console.log(mixedDataTypes, mixedDataTypes.length);
```

## Functions

### Question 8: sumBunnies with no parameters
```javascript
function sumBunnies() {
    let blackBunnies = 10;
    let whiteBunnies = 20;
    return blackBunnies + whiteBunnies;
}
console.log(sumBunnies());
```

### Question 9: sumBunnies with parameters
```javascript
function sumBunnies(blackBunnies, whiteBunnies) {
    return blackBunnies + whiteBunnies;
}
console.log(sumBunnies(10, 20));
console.log(sumBunnies(7, 3));
```

### Question 10: Anonymous and arrow functions
```javascript
const sumAnon = function(blackBunnies, whiteBunnies) {
    return blackBunnies + whiteBunnies;
};
const sumArrow = (blackBunnies, whiteBunnies) => blackBunnies + whiteBunnies;
console.log(sumAnon(10, 20));
console.log(sumArrow(7, 3));
```

### Question 11: Immediately Invoked Function Expression (IIFE)
```javascript
(function() {
    let blackBunnies = 10;
    let whiteBunnies = 20;
    console.log(blackBunnies + whiteBunnies);
})();
```

## Arrays

### Question 12: Modify and print array
```javascript
let bunnies = ['Lucy', 'Tom', 'Molly', 'Bella', 'Daisy', 'Lily'];
bunnies.push('Mario');
bunnies.unshift('Luigi');
bunnies = bunnies.filter(name => name !== 'Lucy');
console.log(bunnies);
```

### Question 13: Array queries
```javascript
const bunnies = ['Lucy', 'Tom', 'Molly', 'Bella'];
console.log(bunnies[0]);
console.log(bunnies[bunnies.length - 1]);
console.log(bunnies.indexOf('Tom'));
console.log([...bunnies]);
```

### Question 14: For loop schedule
```javascript
const bunnies = ['Lucy', 'Tom', 'Molly', 'Bella'];
for (let i = 0; i < bunnies.length; i++) {
    console.log(`Bunny ${bunnies[i]} is scheduled for a checkup today.`);
}
```

### Question 15: Nested arrays extraction
```javascript
const nestedArrays = [['Lucy', 'Tom'], ['Molly', 'Bella']];
console.log(nestedArrays[0][0]); // 'Lucy'
console.log(nestedArrays[1][1]); // 'Bella'
for (let i = 0; i < nestedArrays.length; i++) {
    for (let j = 0; j < nestedArrays[i].length; j++) {
        console.log(nestedArrays[i][j]);
    }
}
```

## JSON

### Question 16: Object to JSON
```javascript
const bunny = { name: 'Lucy', age: 3, isHappy: true };
const bunnyJSON = JSON.stringify(bunny);
console.log(bunnyJSON);
```

### Question 17: JSON to Object
```javascript
let bunnyJSON = '{"name":"Lucy","age":3,"isHappy":true}';
const parsedBunny = JSON.parse(bunnyJSON);
console.log(parsedBunny.name, parsedBunny.age);
```

## Comparison Operators

### Question 18: Equality checks
```javascript
let bunny_age = 3;
let dog_age = '3';
console.log(bunny_age == dog_age);   // true
console.log(bunny_age === dog_age);  // false
console.log(bunny_age != dog_age);   // false
console.log(bunny_age !== dog_age);  // true
```
`==` performs type coercion before comparing, while `===` checks both value and data type without coercing.

### Question 19: Array length comparison
```javascript
const bunnies = ['Lucy', 'Tom'];
const dogs = ['Rover', 'Spot', 'Max'];
if (bunnies.length <= dogs.length) {
    console.log('There are more dogs than bunnies');
} else {
    console.log('There are more bunnies than dogs');
}
```

## Conditional Statements

### Question 20: Health check three ways
```javascript
let health = 'healthy';
// 1. If / else if / else
if (health === 'healthy') {
    console.log('Healthy');
} else if (health === 'sick') {
    console.log('Sick');
} else {
    console.log('Other');
}
// 2. Switch
switch (health) {
    case 'healthy': console.log('Healthy'); break;
    case 'sick': console.log('Sick'); break;
    default: console.log('Other');
}
// 3. Ternary
console.log(health === 'healthy' ? 'Healthy' : 'Not healthy');
```

### Question 21: Even or odd function
```javascript
const checkEvenOdd = num => (num % 2 === 0 ? 'even' : 'odd');
console.log(checkEvenOdd(4));
console.log(checkEvenOdd(7));
console.log(checkEvenOdd(0));
```

## Loops

### Question 22: Ascending loops 0 to 9
```javascript
for (let i = 0; i < 10; i++) { console.log(`Number ${i}`); }
let j = 0;
while (j < 10) { console.log(`Number ${j}`); j++; }
```

### Question 23: Descending countdown 9 to 1
```javascript
let count = 9;
while (count > 0) { console.log(count); count--; }
for (let i = 9; i > 0; i--) { console.log(i); }
```

## Exception Handling and Operators

### Question 24: Try/catch with type validation
```javascript
function sumBunnies(blackBunnies, whiteBunnies) {
    if (typeof blackBunnies !== 'number' || typeof whiteBunnies !== 'number') {
        throw new Error('Arguments must be numbers');
    }
    return blackBunnies + whiteBunnies;
}
try {
    sumBunnies(10, 'twenty');
} catch (error) {
    console.log(error.message);
}
```

### Question 25: Small program with operators and ternary
```javascript
let blackBunnies = 10;
let whiteBunnies = 5;
console.log(blackBunnies === whiteBunnies);
let total = blackBunnies + whiteBunnies;
console.log(total);
console.log(total > 12);
console.log(total > 12 ? 'Yes' : 'No');
```