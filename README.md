# JS Objects

## Objectives

- Model real-world entities.
- Compare entity traits with entity behavior.
- Implement these models with JavaScript objects.
- Contrast the definitions of "property" and "method".

## Preparation

1. Fork and clone this repository.
 [FAQ](https://git.generalassemb.ly/ga-wdi-boston/meta/wiki/ForkAndClone)
1. Create a new branch, `training`, for your work.
1. Checkout to the `training` branch.
1. Install dependencies with `npm install`.

## Introduction
It’s time to learn more about the basic structure that permeates nearly every aspect of JavaScript programming: objects.

You’re probably already more comfortable with objects than you think, because JavaScript loves objects! Many components of the language are actually objects under the hood, and even the parts that aren’t— like strings or numbers— can still act like objects in some instances.

There are only seven fundamental data types in JavaScript, and six of those are the primitive data types: 
- string
- number
- boolean
- null
- undefined
- symbol

With the seventh type, objects, we open our code to more complex possibilities. 
We can use JavaScript objects to model real-world things, like a basketball, a dog, or we can use objects to build the data structures that make the web possible.


![dog objects](https://www.atnyla.com/library/images-tutorials/class-and-object-in-java-6.PNG)

At their core, JavaScript objects are containers storing related data and functionality, but that deceptively simple task is extremely powerful in practice. You’ve been using the power of objects all along, but now it’s time to understand the mechanics of objects and start making your own!

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
Open [./exersises/fasterSpaceship.js](./exersises/fasterSpaceship.js) and follow the instructions.

## Accessing Properties
There are two ways we can access an object’s property. Let’s explore the first way— dot notation, `.`.

You’ve used dot notation to access the properties and methods of built-in objects and data instances:

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
Open [./exersises/countTheCrew.js](./exersises/countTheCrew.js) and follow the instructions.

## Bracket Notation
The second way to access a key’s value is by using bracket notation, `[ ]`.

You’ve used bracket notation when indexing an array:

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
Open [./exersises/secretMission.js](./exersises/secretMission.js) and follow the instructions.

## Property Assignment
Once we’ve defined an object, we’re not stuck with all the properties we wrote. Objects are mutable meaning we can update them after we create them!

We can use either dot notation, `.`, or bracket notation, `[]`, and the assignment operator, ` = ` to add new key-value pairs to an object or change an existing property.

![diagram showing how an object followed by brackets ([]) with the property name as a string can be reassigned to a new value. This same idea applies for accessing a property using dot notation which has the object name, followed by a dot and the name of the property](https://static-assets.codecademy.com/Courses/Learn-JavaScript/objects/object_property_assignment.svg)

One of two things can happen with property assignment:

* If the property already exists on the object, whatever value it held before will be replaced with the newly assigned value.
* If there was no property with that name, a new property will be added to the object.

It’s important to know that although we can’t reassign an object declared with `const`, we can still mutate it, meaning we can add new properties and change the properties that are there.

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
Open [./exersises/spaceshipUpgrade.js](./exersises/spaceshipUpgrade.js) and follow the instructions.



