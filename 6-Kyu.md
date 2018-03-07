# Total Completed: 1

## Take a Ten Minute Walk

https://www.codewars.com/kata/take-a-ten-minute-walk/train/javascript

You live in the city of Cartesia where all roads are laid out in a perfect grid. You arrived ten minutes too early to an appointment, so you decided to take the opportunity to go for a short walk. The city provides its citizens with a Walk Generating App on their phones -- everytime you press the button it sends you an array of one-letter strings representing directions to walk (eg. ['n', 's', 'w', 'e']). You know it takes you one minute to traverse one city block, so create a function that will return true if the walk the app gives you will take you exactly ten minutes (you don't want to be early or late!) and will, of course, return you to your starting point. Return false otherwise.

```javascript
function isValidWalk(walk) {
  let directions = {
    n: 0,
    s: 0,
    w: 0,
    e: 0
  };

  walk.forEach(el => (directions[el] += 1));

  return walk.length == 10 && directions.n === directions.s && directions.w === directions.e;
}
```
