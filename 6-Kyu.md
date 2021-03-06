# Total Completed: 6

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

## Who likes it?

https://www.codewars.com/kata/who-likes-it/javascript

You probably know the "like" system from Facebook and other pages. People can "like" blog posts, pictures or other items. We want to create the text that should be displayed next to such an item.

likes [] // must be "no one likes this"
likes ["Peter"] // must be "Peter likes this"
likes ["Jacob", "Alex"] // must be "Jacob and Alex like this"
likes ["Max", "John", "Mark"] // must be "Max, John and Mark like this"
likes ["Alex", "Jacob", "Mark", "Max"] // must be "Alex, Jacob and 2 others like this"

For more than 4 names, the number in and 2 others simply increases.

```javascript
function likes(names) {
  switch (names.length) {
    case 0:
      return 'no one likes this';
    case 1:
      return `${names} likes this`;
    case 2:
      return `${names[0]} and ${names[1]} like this`;
    case 3:
      return `${names[0]}, ${names[1]} and ${names[2]} like this`;
    default:
      return `${names[0]}, ${names[1]} and ${names.length - 2} others like this`;
  }
}
```

## Which are in?

https://www.codewars.com/kata/which-are-in/javascript

Given two arrays of strings a1 and a2 return a sorted array r in lexicographical order of the strings of a1 which are substrings of strings of a2.

```javascript
function inArray(array1, array2) {
  let r = [];

  for (let str2 of array2) {
    for (let str1 of array1) {
      if (str2.includes(str1)) {
        r.push(str1);
      }
    }
  }

  return Array.from(new Set(r)).sort();
}
```

## Equal Sides Of An Array

https://www.codewars.com/kata/5679aa472b8f57fb8c000047

You are going to be given an array of integers. Your job is to take that array and find an index N where the sum of the integers to the left of N is equal to the sum of the integers to the right of N. If there is no index that would make this happen, return -1.

```javascript
function findEvenIndex(arr) {
  for (let i = 1; i < arr.length - 1; i++) {
    let left = arr.slice(0, i).reduce((acc, curr) => acc + curr);
    let right = arr.slice(i + 1).reduce((acc, curr) => acc + curr);

    if (left === right) {
      return i;
    }
  }
  return -1;
}
```

## Replace With Alphabet Position

https://www.codewars.com/kata/546f922b54af40e1e90001da

In this kata you are required to, given a string, replace every letter with its position in the alphabet.

```javascript
function alphabetPosition(text) {
  let result = ''
  
  for (let i = 0; i < text.length; i++) {
    let upperCaseRange = text.charCodeAt(i) >= 65 && text.charCodeAt(i) <= 90
    let lowerCaseRange = text.charCodeAt(i) >= 97 && text.charCodeAt(i) <= 122

    if (upperCaseRange) result += (text.charCodeAt(i) - 64) + ' '
    if (lowerCaseRange) result += (text.toUpperCase().charCodeAt(i) - 64) + ' '
  }
  
  return result.trimRight()
}
```
