# Practice JS Objects

## Instructions
1. create and checkout to a new brabch called `solution`
2. Create a new directory to type your solutoins

## Solve the following problems: 

1. Given the following code, how can you access the name of the person?

```js
let person = {
  name:       'Bob',
  occupation: 'web developer',
  hobbies:    'painting',
};
```

2. Which of the following values are valid keys for an object?
* `1`
* `'1'`
* `undefined`
* `'hello world'`
* `true`
* `'true'`

3. Use object literal syntax (e.g., `{ key: value, ... }` notation) to create an object that behaves as an array in a for statement. The object should contain at least 3 elements. You should place your code between the braces in the let statement:

```js
let myArray = {
  //your code
  
};

for (let i = 0; i < myArray.length; i += 1) {
  console.log(myArray[i]);
}

```
4. Create an array from the keys of the object `obj` below, with all of the keys converted to uppercase. Your implementation must not mutate `obj`. The order of the array does not matter.

```js
let obj = {
  b: 2,
  a: 1,
  c: 3,
};

```

5. Which of the following values are primitive values? Which are objects? Which are neither?

- `"foo"`
- `3.1415`
- `[ 'a', 'b', 'c' ]`
- `false`
- `foo`
- `function bar() { return "bar"; }`
- `undefined`
- `{ a: 1, b: 2 }`

6. Create a function that creates and returns a copy of an object. The function should take two arguments: the object to copy and an array of the keys that you want to copy. Do not mutate the original object.

The function should let you omit the array of keys argument when calling the function. If you do omit the argument, the function should copy all of the existing keys from the object.

Here are some examples for your reference:

```js
let objToCopy = {
  foo: 1,
  bar: 2,
  qux: 3,
};

let newObj = copyObj(objToCopy);
console.log(newObj);        // => { foo: 1, bar: 2, qux: 3 }

let newObj2 = copyObj(objToCopy, [ 'foo', 'qux' ]);
console.log(newObj2);       // => { foo: 1, qux: 3 }

let newObj3 = copyObj(objToCopy, [ 'bar' ]);
console.log(newObj3);       // => { bar: 2 }
```

