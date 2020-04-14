# Callbacks and higher order function 
## Challenge 1
>Create a function addTwo that accepts one input and adds 2 to it.
```
function addTwo(num) {
  return num + 2;
}
```

## Challenge 2
>Create a function addS that accepts one input and adds an "s" to it.
```function addS(word) {
    return word + 's'
}
```

## Challenge 3
> Create a function called map that takes two inputs:
an array of numbers (a list of numbers)
a 'callback' function - a function that is applied to each element of the array (inside of the function 'map')
Have `map` return a new array filled with numbers that are the result of using the 'callback' function on each element of the input array.

```
function map(array, callback) {
  const newArray = [];
  for (let i = 0; i < array.length; i++) {
      newArray.push(callback(array[i]));
  }
  return newArray;
}

console.log(map([1, 2, 3], addTwo));
```

## Challenge 4
> The function forEach takes an array and a callback, and runs the callback on each element of the array. forEach does not return anything.
let alphabet = '';
const letters = ['a', 'b', 'c', 'd'];
forEach(letters, function(char) {
alphabet += char;
});
console.log(alphabet);   //prints 'abcd'

```
function forEach(array, callback) {
    for (let i = 0; i < array.length; i++) {
    callback(array[i]);
  }
}
```

## Challenge 5
> In the first part of this challenge, you're going to rebuild `map` as `mapWith`. This time you're going to use `forEach` inside of `mapWith` instead of using a `for` loop.

```
function mapWith(array, callback) {
    const newArray = [];
    forEach(array, function(elem) {
        newArray.push(callback(elem));
  });
  return newArray
}
```

```
// trying ES6 with foreach
const tempArray = [2, 5, 7];
tempArray.forEach(elem => addTwo(elem));

console.log(mapWith([1, 2, 3], addTwo));
```

## Challenge 6
>The function reduce takes an array and reduces the elements to a single value. For example it can sum all the numbers, multiply them, or any operation that you can put into a function

```
const add = function(a, b) { return a + b; }

function reduce(array, callback, initialValue) {
  let acc = initialValue;
  for (let i = 0; i < array.length; i++) {
    acc = callback(array[i], acc);
  }
  return acc;

}

console.log(reduce([1, 2, 3], add, 10));
```