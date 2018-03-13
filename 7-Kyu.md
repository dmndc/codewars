# Total Completed: 6

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
