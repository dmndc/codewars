# Total Completed: 4

## Moving Zeros To The End

https://www.codewars.com/kata/52597aa56021e91c93000cb0

Write an algorithm that takes an array and moves all of the zeros to the end, preserving the order of the other elements.

moveZeros([false,1,0,1,2,0,1,3,"a"]) // returns[false,1,1,2,1,3,"a",0,0]

```javascript
var moveZeros = function(arr) {
  var zeros = [];

  for (var i = 0; i < arr.length; i++) {
    if (arr[i] === 0) {
      arr.splice(i, 1);
      zeros.push(0);
      i = i - 1;
    }
  }

  return arr.concat(zeros);
};
```

## Directions Reduction

https://www.codewars.com/kata/550f22f4d758534c1100025a

Write a function dirReduc which will take an array of strings and returns an array of strings with the needless directions removed (W<->E or S<->N side by side).

```javascript
function dirReduc(arr) {
  let a = ['NORTH', 'SOUTH'];
  let b = ['WEST', 'EAST'];

  for (var i = 0; i < arr.length - 1; i++) {
    if (arr[i] !== arr[i + 1]) {
      if ((a.includes(arr[i]) && a.includes(arr[i + 1])) || (b.includes(arr[i]) && b.includes(arr[i + 1]))) {
        arr.splice(i, 2);
        dirReduc(arr);
      }
    }
  }

  return arr;
}
```

## Calculating with Functions

https://www.codewars.com/kata/525f3eda17c7cd9f9e000b39

This time we want to write calculations using functions and get the results. Let's have a look at some examples:

seven(times(five())); // must return 35
four(plus(nine())); // must return 13
eight(minus(three())); // must return 5
six(dividedBy(two())); // must return 3

```javascript
function zero(func) {
  return func ? func(0) : 0;
}
function one(func) {
  return func ? func(1) : 1;
}
function two(func) {
  return func ? func(2) : 2;
}
function three(func) {
  return func ? func(3) : 3;
}
function four(func) {
  return func ? func(4) : 4;
}
function five(func) {
  return func ? func(5) : 5;
}
function six(func) {
  return func ? func(6) : 6;
}
function seven(func) {
  return func ? func(7) : 7;
}
function eight(func) {
  return func ? func(8) : 8;
}
function nine(func) {
  return func ? func(9) : 9;
}

function plus(num2) {
  return function(num1) {
    return num1 + num2;
  };
}
function minus(num2) {
  return function(num1) {
    return num1 - num2;
  };
}
function times(num2) {
  return function(num1) {
    return num1 * num2;
  };
}
function dividedBy(num2) {
  return function(num1) {
    return num1 / num2;
  };
}
```

## String incrementer

https://www.codewars.com/kata/54a91a4883a7de5d7800009c

Your job is to write a function which increments a string, to create a new string. If the string already ends with a number, the number should be incremented by 1. If the string does not end with a number the number 1 should be appended to the new string.

```javascript
function incrementString(str) {
  let word = str.match(/[a-z]+/i);
  let number = str.match(/\d+/);

  function zeroPad(num, length) {
    let str = '' + num;

    while (str.length < length) {
      str = '0' + str;
    }

    return str;
  }

  if (str === '') {
    return '1';
  }

  if (number === null) {
    return word + '1';
  }

  let numLength = number[0].length;
  let increasedNumber = Number(number[0]) + 1;
  let paddedNumber = zeroPad(increasedNumber, numLength);

  if (word === null) {
    return paddedNumber;
  } else {
    return word + paddedNumber;
  }
}
```
