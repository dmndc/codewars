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

## Duplicate Encoder

https://www.codewars.com/kata/duplicate-encoder/javascript

The goal of this exercise is to convert a string to a new string where each character in the new string is '(' if that character appears only once in the original string, or ')' if that character appears more than once in the original string. Ignore capitalization when determining if a character is a duplicate.

Examples:
"din" => "((("
"recede" => "()()()"
"Success" => ")())())"
"(( @" => "))(("

```javascript
function duplicateEncode(word) {
  let chars = {};
  word = word.toLowerCase();

  for (let ch of word) {
    chars[ch] = (chars[ch] || 0) + 1;
  }

  let result = [...word].map(ch => (chars[ch] > 1 ? ')' : '('));

  return result.join('');
}
```
