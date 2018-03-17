# Total Completed: 12

## Credit Card Mask

https://www.codewars.com/kata/5412509bd436bd33920011bc

Usually when you buy something, you're asked whether your credit card number, phone number or answer to your most secret question is still correct. However, since someone could look over your shoulder, you don't want that shown on your screen. Instead, we mask it.

Your task is to write a function maskify, which changes all but the last four characters into '#'.

```javascript
function maskify(cc) {
  let masked = '';
  let lastFour = cc.substr(-4);

  for (var i = 0; i < cc.length - 4; i++) {
    masked += '#';
  }

  return masked + lastFour;
}
```

## Binary Addition

https://www.codewars.com/kata/551f37452ff852b7bd000139

Implement a function that adds two numbers together and returns their sum in binary. The conversion can be done before, or after the addition.

The binary number returned should be a string.

```javascript
function addBinary(a, b) {
  return (a + b).toString(2);
}
```

## Check Coupon

https://www.codewars.com/kata/the-coupon-code/javascript

Your online store likes to give out coupons for special occasions. Some customers try to cheat the system by entering invalid codes or using expired coupons.

Your mission:
Write a function called checkCoupon to verify that a coupon is valid and not expired. If the coupon is good, return true. Otherwise, return false.

```javascript
function checkCoupon(enteredCode, correctCode, currentDate, expirationDate) {
  currentDate = new Date(currentDate);
  expirationDate = new Date(expirationDate);
  if (enteredCode === correctCode && currentDate <= expirationDate) {
    return true;
  } else {
    return false;
  }
}
```

## Sort array by string length

https://www.codewars.com/kata/57ea5b0b75ae11d1e800006c

Write a function that takes an array of strings as an argument and returns a sorted array containing the same strings, ordered from shortest to longest.

```javascript
function sortByLength(array) {
  return array.sort((a, b) => a.length - b.length);
}
```

## Exes and Ohs

https://www.codewars.com/kata/55908aad6620c066bc00002a

Check to see if a string has the same amount of 'x's and 'o's. The method must return a boolean and be case insensitive. The string can contain any char.

```javascript
function XO(str) {
  var numX = 0;
  var numO = 0;

  var array = str.toLowerCase().split('');

  array.forEach(function(item) {
    if (item === 'x') {
      numX++;
    } else if (item === 'o') {
      numO++;
    }
  });

  if (numX === numO || (numX === 0 && numO === 0)) {
    return true;
  } else {
    return false;
  }
}
```

## Square every digit

https://www.codewars.com/kata/546e2562b03326a88e000020

Welcome. In this kata, you are asked to square every digit of a number.
For example, if we run 9119 through the function, 811181 will come out, because 92 is 81 and 12 is 1.

```javascript
function squareDigits(num) {
  let digits = Array.from(num.toString()).map(Number);

  return Number(
    digits
      .map(function(x) {
        return Math.pow(x, 2);
      })
      .join('')
  );
}
```

## Shortest word

https://www.codewars.com/kata/57cebe1dc6fdc20c57000ac9

Simple, given a string of words, return the length of the shortest word(s).

```javascript
function findShort(s) {
  words = s.split(' ').sort((a, b) => a.length - b.length);
  return words[0].length;
}
```

## Descending order

https://www.codewars.com/kata/5467e4d82edf8bbf40000155

Your task is to make a function that can take any non-negative integer as a argument and return it with its digits in descending order. Essentially, rearrange the digits to create the highest possible number.

```javascript
function descendingOrder(n) {
  return Number(
    ('' + n)
      .split('')
      .sort((a, b) => b - a)
      .join('')
  );
}
```

## Sum of integers in string

https://www.codewars.com/kata/598f76a44f613e0e0b000026

Your task in this kata is to implement a function that calculates the sum of the integers inside a string. For example, in the string "The30quick20brown10f0x1203jumps914ov3r1349the102l4zy dog", the sum of the integers is 3635.

```javascript
function sumOfIntegersInString(s) {
  const numbers = s.match(/\d+/g);

  if (numbers) {
    return numbers.map(Number).reduce((a, b) => a + b);
  } else {
    return 0;
  }
}
```

## Sum of two lowest positive integers

https://www.codewars.com/kata/558fc85d8fd1938afb000014

Create a function that returns the sum of the two lowest positive numbers given an array of minimum 4 integers. No floats or empty arrays will be passed.
For example, when an array is passed like [19, 5, 42, 2, 77], the output should be 7.

```javascript
function sumTwoSmallestNumbers(numbers) {
  let sortedNums = numbers.sort((a, b) => a - b);
  return sortedNums[0] + sortedNums[1];
}
```

## Sort array by string length

https://www.codewars.com/kata/57ea5b0b75ae11d1e800006c

Write a function that takes an array of strings as an argument and returns a sorted array containing the same strings, ordered from shortest to longest.

```javascript
function sortByLength(array) {
  return array.sort((a, b) => a.length - b.length);
}
```

## Factorial

https://www.codewars.com/kata/54ff0d1f355cfd20e60001fc

In mathematics, the factorial of a non-negative integer n, denoted by n!, is the product of all positive integers less than or equal to n. For example: 5! = 5 * 4 * 3 * 2 * 1 = 120. By convention the value of 0! is 1.

```javascript
function factorial(n) {

  let i = n;
  let num = 1;
  
  if (n === 0) {
    return 1;
  }
  
  if (n < 0 || n > 12) {
     throw new RangeError;
  }
  
  while (i > 1) {
    num *= i;
    i--  
  }
  
  return num;  

}
```