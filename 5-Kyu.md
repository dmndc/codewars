# Total Completed: 6

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

## Valid Parentheses

https://www.codewars.com/kata/valid-parentheses/javascript

Write a function called that takes a string of parentheses, and determines if the order of the parentheses is valid. The function should return true if the string is valid, and false if it's invalid.

Examples
"()" => true
")(()))" => false
"(" => false
"(())((()())())" => true

```javascript
function validParentheses(parens) {
  let count = 0;

  for (let i = 0; i < parens.length; i += 1) {
    if (parens[i] === '(') count += 1;
    if (parens[i] === ')') {
      if (count === 0) return false;
      count -= 1;
    }
  }

  return count === 0;
}
```

## Scramblies

https://www.codewars.com/kata/scramblies/javascript

Write function scramble(str1,str2) that returns true if a portion of str1 characters can be rearranged to match str2, otherwise returns false.

For example:
str1 is 'rkqodlw' and str2 is 'world' the output should return true.
str1 is 'cedewaraaossoqqyt' and str2 is 'codewars' should return true.
str1 is 'katas' and str2 is 'steak' should return false.

```javascript
function scramble(str1, str2) {
  let chars = {};

  for (let i = 0; i < str1.length; i++) {
    chars[str1[i]] = (chars[str1[i]] || 0) + 1;
  }

  for (let j = 0; j < str2.length; j++) {
    if (chars[str2[j]] === undefined || chars[str2[j]] < 1) {
      return false;
    } else {
      chars[str2[j]] = chars[str2[j]] - 1;
    }
  }

  return true;
}
```
