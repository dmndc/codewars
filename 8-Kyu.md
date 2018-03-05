# Total Completed: 5

## Check your arrows

https://www.codewars.com/kata/559f860f8c0d6c7784000119

You have a quiver of arrows, but some have been damaged. The quiver contains arrows with an optional range information (different types of targets are positioned at different ranges), so each item is an arrow.
You need to verify that you have some good ones left, in order to prepare for battle:

anyArrows([{range: 5}, {range: 10, damaged: true}, {damaged: true}])
If an arrow in the quiver does not have a damaged status, it means it's new.

The expected result is a boolean, indicating whether you have any good arrows left.

```javascript
function anyArrows(arrows) {
  return arrows.some(elem => elem.damaged !== true);
}
```

## Find Maximum and Minimum Values of a List

https://www.codewars.com/kata/577a98a6ae28071780000989

Your task is to make two functions, max and min (maximum and minimum in PHP) that take a(n) array/vector of integers list as input and outputs, respectively, the largest and lowest number in that array/vector.

#Examples

max([4,6,2,1,9,63,-134,566]) returns 566
min([-52, 56, 30, 29, -54, 0, -110]) returns -110
max([5]) returns 5
min([42, 54, 65, 87, 0]) returns 0
#Notes

You may consider that there will not be any empty arrays/vectors.

```javascript
var min = function(list) {
  return Math.min(...list);
};

var max = function(list) {
  return Math.max(...list);
};
```

## Remove the time

https://www.codewars.com/kata/56b0ff16d4aa33e5bb00008e

You're re-designing a blog and the blog's posts have the following format for showing the date and time a post was made:

Weekday Month Day, time e.g., Friday May 2, 7pm

You're running out of screen real estate, and on some pages you want to display a shorter format, Weekday Month Day that omits the time.

Write a function, shortenToDate, that takes the Website date/time in its original string format, and returns the shortened format.

Assume shortenToDate's input will always be a string, e.g. "Friday May 2, 7pm". Assume shortenToDate's output will be the shortened string, e.g., "Friday May 2".

```javascript
function shortenToDate(longDate) {
  return longDate.substring(0, longDate.indexOf(','));
}
```

## Days in the year

https://www.codewars.com/kata/56d6c333c9ae3fc32800070f

A variation of determining leap years, assuming only integers are used and years can be negative and positive.

Write a function which will return the days in the year and the year entered in a string. For example 2000, entered as an integer, will return as a string 2000 has 366 days

There are a few assumptions we will accept the year 0, even though there is no year 0 in the Gregorian Calendar.

Also the basic rule for validating a leap year are as follows

Most years that can be divided evenly by 4 are leap years.

Exception: Century years are NOT leap years UNLESS they can be evenly divided by 400.

So the years 0, -64 and 2016 will return 366 days. Whilst 1974, -10 and 666 will return 365 days.

```javascript
function yearDays(year) {
  if (year % 4 !== 0) {
    return year + ' has 365 days';
  } else if (year % 100 !== 0) {
    return year + ' has 366 days';
  } else if (year % 400 !== 0) {
    return year + ' has 365 days';
  } else {
    return year + ' has 366 days';
  }
}
```

## UEFA EURO 2016

https://www.codewars.com/kata/57613fb1033d766171000d60

Finish the uefaEuro2016() function so it return string just like in the examples below:

uefaEuro2016(['Germany', 'Ukraine'],[2, 0]) // "At match Germany - Ukraine, Germany won!"
uefaEuro2016(['Belgium', 'Italy'],[0, 2]) // "At match Belgium - Italy, Italy won!"
uefaEuro2016(['Portugal', 'Iceland'],[1, 1]) // "At match Portugal - Iceland, teams played draw."

```javascript
function uefaEuro2016(teams, scores) {
  var teamA = teams[0];
  var teamB = teams[1];

  if (scores[0] > scores[1]) {
    return 'At match ' + teamA + ' - ' + teamB + ', ' + teamA + ' won!';
  } else if (scores[0] < scores[1]) {
    return 'At match ' + teamA + ' - ' + teamB + ', ' + teamB + ' won!';
  } else if (scores[0] === scores[1]) {
    return 'At match ' + teamA + ' - ' + teamB + ', teams played draw.';
  }
}
```
