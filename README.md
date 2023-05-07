# Objects

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
### exercises
Open [exersises/fasterSpaceship.js](exersises/fasterSpaceship.js) and follow the instructions.


