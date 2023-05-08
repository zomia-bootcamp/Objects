# JS Objects

## Objectives

- Implement models of real-world entities using JavaScript objects.
- Differentiate between "property" and "method" definitions.
- Modify object properties.
- Access objects by reference.

## Preparation

1. Fork and clone this repository.
 [FAQ](https://git.generalassemb.ly/ga-wdi-boston/meta/wiki/ForkAndClone)
1. Create a new branch, `training`, for your work.
1. Checkout to the `training` branch.
1. Install dependencies with `npm install`.

### Introduction

It is time to delve deeper into the fundamental structure that underlies almost every aspect of JavaScript programming: objects.

You might already be more familiar with objects than you think, as JavaScript embraces them. Many components of the language are actually objects internally, and even those that are not, like strings or numbers, can still exhibit object-like behavior in certain situations.

JavaScript has only seven fundamental data types, with six of them being primitive data types:
- string
- number
- boolean
- null
- undefined
- symbol

With the seventh type, objects, we unlock more complex possibilities in our code. JavaScript objects can be used to represent real-world entities such as a basketball or a dog, or they can be used to construct the data structures that power the web.

![dog objects](https://www.atnyla.com/library/images-tutorials/class-and-object-in-java-6.PNG)

At their core, JavaScript objects act as containers that hold related data and functionality. Despite their seemingly simple nature, objects possess remarkable power in practice. You have already been harnessing the power of objects, but now it is time to understand their mechanics and create your own!

## Creating Object Literals
Objects can be assigned to variables just like any JavaScript type. We use curly braces, `{}`, to designate an object literal:
```js
let spaceship = {}; // spaceship is an empty object
```
We fill an object with unordered data. This data is organized into key-value pairs. A key is like a variable name that points to a location in memory that holds a value.

![key value pairs](https://education.launchcode.org/intro-to-professional-web-dev/_images/object.png)

A key’s value can be of any data type in the language including functions or other objects.

We make a key-value pair by writing the key’s name, or identifier, followed by a colon and then the value. We separate each key-value pair in an object literal with a comma (,). Keys are strings, but when we have a key that does not have any special characters in it, JavaScript allows us to omit the quotation marks:

![object example](https://static-assets.codecademy.com/Courses/learn-javascript-objects/javascript_object.svg)
```js
// An object literal with two key-value pairs
let spaceship = {
  'Fuel Type': 'diesel',
  color: 'silver'
};
```
The `spaceship` object has two properties `Fuel Type` and `color`. `'Fuel Type'` has quotation marks because it contains a space character.
### Exercises
Open [./exercises/fasterSpaceship.js](./exercises/fasterSpaceship.js) and follow the instructions.

## Accessing Properties

There are two ways to access an object's property. Let's explore the first way: dot notation (`.`).

You have already used dot notation to access properties and methods of built-in objects and data instances:

```js 'hello'.length; // Returns 5 ```
With property dot notation, we write the object’s name, followed by the dot operator and then the property name (key):

```js
let spaceship = {
  homePlanet: 'Earth',
  color: 'silver'
};
spaceship.homePlanet; // Returns 'Earth',
spaceship.color; // Returns 'silver',
```
![dot notation](https://content.codecademy.com/courses/learn-javascript-objects/object%20dot%20notation.svg)

If we try to access a property that does not exist on that object, `undefined` will be returned.

```js
spaceship.favoriteIcecream; // Returns undefined
```
Let’s get some more practice using dot notation on an object!

### Exercises
Open [./exercises/countTheCrew.js](./exercises/countTheCrew.js) and follow the instructions.

## Bracket Notation

The second way to access a key's value is by using bracket notation (`[ ]`).

You have already used bracket notation when indexing an array:

```js
['A', 'B', 'C'][0]; // Returns 'A'
```
To use bracket notation to access an object’s property, we pass in the property name (key) as a string.

![bracket notation](https://content.codecademy.com/courses/learn-javascript-objects/object%20access%20bracket.svg)

We must use bracket notation when accessing keys that have numbers, spaces, or special characters in them. Without bracket notation in these situations, our code would throw an error.

```js
let spaceship = {
  'Fuel Type': 'Turbo Fuel',
  'Active Duty': true,
  homePlanet: 'Earth',
  numCrew: 5
};
spaceship['Active Duty'];   // Returns true
spaceship['Fuel Type'];   // Returns  'Turbo Fuel'
spaceship['numCrew'];   // Returns 5
spaceship['!!!!!!!!!!!!!!!'];   // Returns undefined
```
With bracket notation you can also use a variable inside the brackets to select the keys of an object. This can be especially helpful when working with functions:

``` js 
let returnAnyProp = (objectName, propName) => objectName[propName]; 
 
returnAnyProp(spaceship, 'homePlanet'); // Returns 'Earth'
```
If we tried to write our `returnAnyProp()` function with dot notation (objectName.propName) the computer would look for a #key# of `'propName'` on our object and not the #value# of the `propName` parameter.

### Exercises
Open [./exercises/secretMission.js](./exercises/secretMission.js) and follow the instructions.

## Property Assignment

Once we've defined an object, we're not stuck with all the properties we initially wrote. Objects are mutable, which means we can update them after creating them.

To add new key-value pairs to an object or change an existing property, we can use either dot notation (`.`) or bracket notation (`[]`) along with the assignment operator (`=`).
Here's how we can perform property assignment:


![diagram showing how an object followed by brackets ([]) with the property name as a string can be reassigned to a new value. This same idea applies for accessing a property using dot notation which has the object name, followed by a dot and the name of the property](https://static-assets.codecademy.com/Courses/Learn-JavaScript/objects/object_property_assignment.svg)

One of two things can happen with property assignment:

* If the property already exists on the object, the new value will replace the old value.
* If there was no property with that name, a new property will be added to the object.

Please note that while we can't reassign an object declared with const, we can still mutate it by adding new properties or changing existing ones.

```js
const spaceship = {type: 'shuttle'};
spaceship = {type: 'alien'}; // TypeError: Assignment to constant variable.
spaceship.type = 'alien'; // Changes the value of the type property
spaceship.speed = 'Mach 5'; // Creates a new key of 'speed' with a value of 'Mach 5'
```

You can delete a property from an object with the `delete` operator.

```js
const spaceship = {
  'Fuel Type': 'Turbo Fuel',
  homePlanet: 'Earth',
  mission: 'Explore the universe' 
};
 
delete spaceship.mission;  // Removes the mission property
```

### Exercises
Open [./exercises/spaceshipUpgrade.js](./exercises/spaceshipUpgrade.js) and follow the instructions.

## Methods

Methods in JavaScript refer to functions that are stored within objects. They define the actions that an object can perform. In contrast, properties represent the characteristics or data that an object possesses.

You might already be familiar with object methods without realizing it. For example, the `console` object in JavaScript provides a method called `.log()` for printing messages to the console. Similarly, the `Math` object includes a method called `.floor()` for rounding numbers down to the nearest integer.

To define methods in JavaScript objects, we use key-value pairs separated by colons. The key represents the name of the method, while the value is an anonymous function expression.

By using methods, we can make objects in JavaScript more dynamic and functional. They allow objects to perform specific actions and provide a way to organize and encapsulate related functionality within the object itself.

```js
const alienShip = {
  invade: function () { 
    console.log('Hello! We have come to dominate your planet. Instead of Earth, it shall be called New Xaculon.')
  }
};
```
With the new method syntax introduced in ES6 we can omit the colon and the `function` keyword.

```js
const alienShip = {
  invade () { 
    console.log('Hello! We have come to dominate your planet. Instead of Earth, it shall be called New Xaculon.')
  }
};
```
Object methods are invoked by appending the object’s name with the dot operator followed by the method name and parentheses:

```js
alienShip.invade(); // Prints 'Hello! We have come to dominate your planet. Instead of Earth, it shall be called New Xaculon.'
```

### Exercises
Open [./exercises/retreat.js](./exercises/retreat.js) and follow the instructions.

## Nested Objects

In programming, objects can be nested, which means that an object can have another object as one of its properties. This allows us to organize and structure our data hierarchically.

For example, imagine a `spaceship` object. Inside this object, we can have a `crew` object that represents the crew members on the spaceship. Each crew member is an object with properties like `name` and `degree`. We can also nest other objects within the `spaceship`, such as a `telescope` object or details about the spaceship's computers in a `nanoelectronics` object.

By nesting objects, we can create complex data structures that represent real-world scenarios and the relationships between different entities.

```js
const spaceship = {
     telescope: {
        yearBuilt: 2018,
        model: '91031-XLT',
        focalLength: 2032 
     },
    crew: {
        captain: { 
            name: 'Sandra', 
            degree: 'Computer Engineering', 
            encourageTeam() { console.log('We got this!') } 
         }
    },
    engine: {
        model: 'Nimbus2000'
     },
     nanoelectronics: {
         computer: {
            terabytes: 100,
            monitors: 'HD'
         },
        'back-up': {
           battery: 'Lithium',
           terabytes: 50
         }
    }
}; 
```
## Chaining Operators to Access Nested Properties

When working with nested objects, we can chain operators together to access properties at different levels. To do this, we need to choose the appropriate operator for each layer of the nested structure.

To make it easier, imagine yourself as the computer and evaluate each expression from left to right. This approach helps break down the operations and make them more manageable.

```js
spaceship.nanoelectronics['back-up'].battery; // Returns 'Lithium'
```
In the preceding code:

* First the computer evaluates `spaceship.nanoelectronics`, which results in an object containing the `back-up` and `computer` objects.
* We accessed the `back-up` object by appending `['back-up']`.
* The `back-up` object has a `battery` property, accessed with `.battery` which returned the value stored there: `'Lithium'`

### Exercises
Open [./exercises/onBoard.js](./exercises/onBoard.js) and follow the instructions.

## Pass By Reference

When working with objects in JavaScript, they are passed by reference. This means that when we pass an object variable as an argument to a function, the parameter name inside the function refers to the same object in memory. Consequently, any changes made to the object's properties within the function will permanently modify the original object, even if it is assigned to a `const` variable.


```js
const spaceship = {
  homePlanet : 'Earth',
  color : 'silver'
};
 
let paintIt = obj => {
  obj.color = 'glorious gold'
};
 
paintIt(spaceship);
 
spaceship.color // Returns 'glorious gold'
```
 
Our function `paintIt()` permanently changed the color of our `spaceship` object. However, reassignment of the `spaceship` variable wouldn’t work in the same way:

```js
let spaceship = {
  homePlanet : 'Earth',
  color : 'red'
};
let tryReassignment = obj => {
  obj = {
    identified : false, 
    'transport type' : 'flying'
  }
  console.log(obj) // Prints {'identified': false, 'transport type': 'flying'}
 
};
tryReassignment(spaceship) // The attempt at reassignment does not work.
spaceship // Still returns {homePlanet : 'Earth', color : 'red'};
 
spaceship = {
  identified : false, 
  'transport type': 'flying'
}; // Regular reassignment still works.
```

Let’s look at what happened in the code example:

- We declared a `spaceship` object using `let`. This allowed us to reassign it to a new object with properties like `identified` and `transport type` without any issues.
- However, when we passed the `spaceship` object into a function designed to reassign the object, the reassignment didn't have any effect (even though printing the object using `console.log()` gave us the expected result).

- The reason for this is that when we passed `spaceship` into the function, the function's parameter (`obj`) became a reference to the memory location of the `spaceship` object, not to the `spaceship` variable itself. The function has no knowledge of the `spaceship` variable.
- So when we performed the reassignment inside the function, the `obj` variable started referring to a new object `{'identified': false, 'transport type': 'flying'}`, while the `spaceship` variable remained unchanged.


### Exercises
Open [./exercises/energise.js](./exercises/energise.js) and follow the instructions.

## Looping Through Objects
### Self Study
Loops are programming tools that repeat a block of code until a condition is met. We learned how to iterate through arrays using their numerical indexing, but the key-value pairs in objects aren’t ordered! JavaScript has given us an [alternative solution](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...in) for iterating through objects with the for...in syntax .

`for...in` will execute a given block of code for each property in an object.

```js
let spaceship = {
  crew: {
    captain: { 
      name: 'Lily', 
      degree: 'Computer Engineering', 
      cheerTeam() { console.log('You got this!') } 
    },
    'chief officer': { 
      name: 'Dan', 
      degree: 'Aerospace Engineering', 
      agree() { console.log('I agree, captain!') } 
    },
    medic: { 
      name: 'Clementine', 
      degree: 'Physics', 
      announce() { console.log(`Jets on!`) } },
    translator: {
      name: 'Shauna', 
      degree: 'Conservation Science', 
      powerFuel() { console.log('The tank is full!') } 
    }
  }
}; 
 
// for...in
for (let crewMember in spaceship.crew) {
  console.log(`${crewMember}: ${spaceship.crew[crewMember].name}`);
}
```
Our `for...in` will iterate through each element of the `spaceship.crew` object. In each iteration, the variable `crewMember` is set to one of `spaceship.crew`‘s keys, enabling us to log a list of crew members’ role and `name`.

### Exercises
Open [./exercises/crewInfo.js](./exercises/crewInfo.js) and follow the instructions.
