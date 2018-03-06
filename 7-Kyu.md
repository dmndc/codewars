# Total Completed: 3

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
