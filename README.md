<div align="center">
  <img height="60" src="./assets/codewars_button_icon.png">
  <h1>30 Days Codewars</h1>

---

<span>Hello 🌏! I like solving coding problems, especially on <a href="https://www.codewars.com/">codewars</a>. So, I decided to share my 30-days-of-solving-codewars-problems journey here.</span>

<span>Everyday I will solve one question from codewars and share below. It will include the question, my answer and one or two best answers from the codewars community.</span>

Ways to reach out to me 👇 <br />
<a target="_blank" href="https://twitter.com/nomanoff_tech">Twitter</a> || <a href="https://www.linkedin.com/in/me-adam/">LinkedIn</a> || <a href="https://dev.to/nomanoff_tech">Blogs</a>

_Btw, if you find some typos, feel free to leave a PR 😎_

</div>

---

<details><summary><b>Day 0</b></summary>

#### Even or Odd?

> 8 kyu

###### Description:

> Create a function that takes an integer as an argument and returns "Even" for even numbers or "Odd" for odd numbers.

```javascript
function even_or_odd(number) {}

even_or_odd();
```

<details><summary><b>My Answer</b></summary>

```javascript
function even_or_odd(number) {
  return number % 2 === 0 ? "Even" : "Odd";
}
```

</details>

<details><summary><b>Best Answer</b></summary>

```javascript
function even_or_odd(number) {
  return number % 2 ? "Odd" : "Even";
}
```

</details>

</details>

---

<details><summary><b>Day 1</b></summary>

#### Stop gninnipS My sdroW!

> 6 kyu

###### Description:

> Write a function that takes in a string of one or more words, and returns the same string, but with all five or more letter words reversed (Just like the name of this Kata). Strings passed in will consist of only letters and spaces. Spaces will be included only when more than one word is present.

> Examples: spinWords( "Hey fellow warriors" ) => returns "Hey wollef sroirraw" spinWords( "This is a test") => returns "This is a test" spinWords( "This is another test" )=> returns "This is rehtona test"

```javascript
function spinWords(string) {
  //TODO Have fun :)
}
```

<details><summary><b>My Answer 😅</b></summary>

```javascript
function spinWords(string) {
  let words = string.split(" ");

  let newWords = words.map((word) =>
    word.length >= 5 ? word.split("").reverse().join("") : word
  );

  return newWords.join(" ");
}
```

</details>

<details><summary><b>Best Answers ✅</b></summary>

> Top ranked answer (writter by a human 😅):

```javascript
function spinWords(words) {
  return words
    .split(" ")
    .map(function (word) {
      return word.length > 4 ? word.split("").reverse().join("") : word;
    })
    .join(" ");
}
```

> 2nd ranked answer 👀:

```javascript
function spinWords(string){
  return string.replace(/\w{5,}/g, function(w) { return w.split('').reverse().join('') })
}
}
```

</details>

</details>

---

<details><summary><b>Day 2</b></summary>

#### Sum of Digits / Digital Root

> 6 kyu

###### Description:

> [Digital root](https://en.wikipedia.org/wiki/Digital_root) is the recursive sum of all the digits in a number.

> Given n, take the sum of the digits of n. If that value has more than one digit, continue reducing in this way until a single-digit number is produced. The input will be a non-negative integer.

> Examples:

```javascript
    16  -->  1 + 6 = 7
   942  -->  9 + 4 + 2 = 15  -->  1 + 5 = 6
132189  -->  1 + 3 + 2 + 1 + 8 + 9 = 24  -->  2 + 4 = 6
493193  -->  4 + 9 + 3 + 1 + 9 + 3 = 29  -->  2 + 9 = 11  -->  1 + 1 = 2
```

> Start here:

```javascript
function digital_root(n) {
  // ...
}
```

<details><summary><b>My Answer 😅</b></summary>

```javascript
function digital_root(n) {
  let newNum;
  let justNum = n
    .toString()
    .split("")
    .map((num) => parseInt(num, 10));

  newNum = justNum.reduce((partialSum, a) => partialSum + a, 0);

  if (newNum.toString().length > 1) {
    return digital_root(newNum);
  } else {
    return newNum;
  }
}
```

</details>

<details><summary><b>Best Answers ✅</b></summary>

> Top ranked answer, wtf? 🤯:

```javascript
function digital_root(n) {
  return ((n - 1) % 9) + 1;
}
```

<details><summary><b>Top comments for this solution. Just read for fun 😅</b></summary>

> - dude speaks matrix languague

> - mathematics!

> - what kind of sorcery is this?

> - my brain is damaged!

> - wait, what?

> - hmmm... wtf? totally mind boggling

> - bruh!!!

> - I am not a coder.

> - The simplicity is extremely frustrating. Thank you

> - I am quitting programming after this

</details>

> 2nd ranked answer 👍:

```javascript
function digital_root(n) {
  if (n < 10) return n;

  return digital_root(
    n
      .toString()
      .split("")
      .reduce(function (acc, d) {
        return acc + +d;
      }, 0)
  );
}
```

</details>

</details>

---

<details><summary><b>Day 3</b></summary>

#### Disemvowel Trolls

> 7 kyu

###### Description:

> Trolls are attacking your comment section! A common way to deal with this situation is to remove all of the vowels from the trolls' comments, neutralizing the threat. Your task is to write a function that takes a string and return a new string with all vowels removed. For example, the string "This website is for losers LOL!" would become "Ths wbst s fr lsrs LL!".

> Note: for this kata y isn't considered a vowel.

```javascript
function disemvowel(str) {
  return str;
}
```

<details><summary><b>My Answer 😅</b></summary>

```javascript
function disemvowel(str) {
  return str
    .split(" ")
    .map((x) => x.replace(/[aAeEiIoOuU]/g, ""))
    .join(" ");
}
```

</details>

<details><summary><b>Best Answers ✅</b></summary>

> Top ranked answer (writter by a human 😅):

```javascript
function disemvowel(str) {
  return str.replace(/[aeiou]/gi, "");
}
```

> 2nd ranked answer 👀:

```javascript
function disemvowel(str) {
  var vowels = ["a", "e", "i", "o", "u"];

  return str
    .split("")
    .filter(function (el) {
      return vowels.indexOf(el.toLowerCase()) == -1;
    })
    .join("");
}
```

</details>

</details>

---

<details><summary><b>Day 4</b></summary>

#### Array.diff

> 6 kyu

###### Description:

> Your goal in this kata is to implement a difference function, which subtracts one list from another and returns the result.

> It should remove all values from list a, which are present in list b keeping their order.

```javascript
arrayDiff([1, 2], [1]) == [2];
```

> If a value is present in b, all of its occurrences must be removed from the other:

```javascript
arrayDiff([1, 2, 2, 2, 3], [2]) == [1, 3];
```

<details><summary><b>My Answers 😅</b></summary>

```javascript
// Solution 1:
function arrayDiff(a, b) {
  return a.filter((val) => !b.includes(val));
}

// Solution 2:
function arrayDiff(a, b) {
  return a.filter((val) => b.indexOf(val) === -1);
}
```

</details>

<details><summary><b>Best Answers ✅</b></summary>

> Top ranked answer 🤯:

```javascript
function array_diff(a, b) {
  return a.filter((e) => !b.includes(e));
}
```

> 2nd ranked answer 👍:

```javascript
function array_diff(a, b) {
  return a.filter(function (x) {
    return b.indexOf(x) == -1;
  });
}
```

</details>

</details>

---

<details><summary><b>Day 5</b></summary>

####

> 7 kyu

###### Description:

> In this little assignment you are given a string of space separated numbers, and have to return the highest and lowest number.

> _Examples:_

```javascript
highAndLow("1 2 3 4 5"); // return "5 1"
highAndLow("1 2 -3 4 5"); // return "5 -3"
highAndLow("1 9 3 4 -5"); // return "9 -5"
```

> _Notes:_

- All numbers are valid Int32, no need to validate them.
- There will always be at least one number in the input string.
- Output string must be two numbers separated by a single space, and highest number is first.

<details><summary><b>My Answer 😅</b></summary>

```javascript
function highAndLow(numbers) {
  let n1 = numbers.split(" ").reduce((a, b) => `${Math.min(a, b)}`);
  let n2 = numbers.split(" ").reduce((a, b) => `${Math.max(a, b)}`);

  return `${n2} ${n1}`;
}
```

</details>

<details><summary><b>Best Answers ✅</b></summary>

> Top ranked answer 🤯:

```javascript
function highAndLow(numbers) {
  numbers = numbers.split(" ").map(Number);
  return Math.max.apply(0, numbers) + " " + Math.min.apply(0, numbers);
}
```

> 2nd ranked answer 👍:

```javascript
function highAndLow(numbers) {
  numbers = numbers.split(" ");
  return `${Math.max(...numbers)} ${Math.min(...numbers)}`;
}
```

</details>

</details>

---

<details><summary><b>Day 5*</b></summary>

####

> 6 kyu

###### Description:

> Jamie is a programmer, and James' girlfriend. She likes diamonds, and wants a diamond string from James. Since James doesn't know how to make this happen, he needs your help.

> You need to return a string that looks like a diamond shape when printed on the screen, using asterisk (\*) characters. Trailing spaces should be removed, and every line must be terminated with a newline character (\n).

> Return `null/nil/None/...` if the input is an even number or negative, as it is not possible to print a diamond of even or negative size.

###### Examples

_A size 3 diamond:_

```javascript
 *
***
 *
```

...which would appear as a string of `" *\n***\n *\n"`

_A size 5 diamond:_

```javascript
  *
 ***
*****
 ***
  *
```

...that is:

`" *\n ***\n*****\n ***\n *\n"`

<details><summary><b>My Answer 😅</b></summary>

> Sorry, I couldn't think of an answer for this one so I had to unlock the solution 😅
> So, I don't count this one 😉

</details>

<details><summary><b>Best Answers ✅</b></summary>

> Top ranked answer 🤯:

```javascript
function diamond(n) {
  if (n <= 0 || n % 2 === 0) return null;
  str = "";
  for (let i = 0; i < n; i++) {
    let len = Math.abs((n - 2 * i - 1) / 2);
    str += " ".repeat(len);
    str += "*".repeat(n - 2 * len);
    str += "\n";
  }
  return str;
}
```

> 2nd ranked answer 👍:

```javascript
function diamond(n) {
  if (n % 2 == 0 || n < 1) return null;
  var x = 0,
    add,
    diam = line(x, n);
  while ((x += 2) < n) {
    add = line(x / 2, n - x);
    diam = add + diam + add;
  }
  return diam;
} //z.

function repeat(str, x) {
  return Array(x + 1).join(str);
}
function line(spaces, stars) {
  return repeat(" ", spaces) + repeat("*", stars) + "\n";
}
```

</details>

</details>

---

<details><summary><b>Day 6 (1)</b></summary>

####

> 6 kyu

###### Description:

> You probably know the "like" system from Facebook and other pages. People can "like" blog posts, pictures or other items. We want to create the text that should be displayed next to such an item.

> Implement the function which takes an array containing the names of people that like an item. It must return the display text as shown in the examples:

```javascript
[]                                -->  "no one likes this"
["Peter"]                         -->  "Peter likes this"
["Jacob", "Alex"]                 -->  "Jacob and Alex like this"
["Max", "John", "Mark"]           -->  "Max, John and Mark like this"
["Alex", "Jacob", "Mark", "Max"]  -->  "Alex, Jacob and 2 others like this"
```

> Note: For 4 or more names, the number in `"and 2 others"` simply increases.

<details><summary><b>My solution 😅</b></summary>

```javascript
function likes(names) {
  if (names.length === 0) {
    return "no one likes this";
  } else if (names.length === 1) {
    return `${names[0]} likes this`;
  } else if (names.length === 2) {
    return `${names[0]} and ${names[1]} like this`;
  } else if (names.length === 3) {
    return `${names[0]}, ${names[1]} and ${names[2]} like this`;
  }
  return `${names[0]}, ${names[1]} and ${names.length - 2} others like this`;
}
```

</details>

<details><summary><b>Best solutions ✅</b></summary>

> Top ranked answer (...meh) 👍:

```javascript
function likes(names) {
  names = names || [];
  switch (names.length) {
    case 0:
      return "no one likes this";
      break;
    case 1:
      return names[0] + " likes this";
      break;
    case 2:
      return names[0] + " and " + names[1] + " like this";
      break;
    case 3:
      return names[0] + ", " + names[1] + " and " + names[2] + " like this";
      break;
    default:
      return (
        names[0] +
        ", " +
        names[1] +
        " and " +
        (names.length - 2) +
        " others like this"
      );
  }
}
```

> 2nd ranked answer (clever 😁):

```javascript
function likes(names) {
  return {
    0: "no one likes this",
    1: `${names[0]} likes this`,
    2: `${names[0]} and ${names[1]} like this`,
    3: `${names[0]}, ${names[1]} and ${names[2]} like this`,
    4: `${names[0]}, ${names[1]} and ${names.length - 2} others like this`,
  }[Math.min(4, names.length)];
}
```

</details>

</details>

---

<details><summary><b>Day 6 (2)</b></summary>

####

> 7 kyu

###### Description:

> Your task is to make a function that can take any non-negative integer as an argument and return it with its digits in descending order. Essentially, rearrange the digits to create the highest possible number.

> Examples:

Input: `42145` Output: `54421`

Input:` 145263` Output: `654321`

Input: `123456789` Output: `987654321`

<details><summary><b>My solution 😅</b></summary>

```javascript
function descendingOrder(n) {
  let str = n
    .toString()
    .split("")
    .sort((a, b) => a - b)
    .reverse()
    .join("");

  return parseInt(str, 10);
}
```

</details>

<details><summary><b>Best solutions ✅</b></summary>

> Top ranked answer 👍:

```javascript
function descendingOrder(n) {
  return parseInt(String(n).split("").sort().reverse().join(""));
}
```

> 2nd ranked answer ✅:

```javascript
function descendingOrder(n) {
  return +(n + "")
    .split("")
    .sort(function (a, b) {
      return b - a;
    })
    .join("");
}
```

</details>

</details>

---

<details><summary><b>Day 7</b></summary>

####

> 6 kyu

###### Description:

>

> Examples:

<details><summary><b>My solution 😅</b></summary>

> tolerable 🥱

```javascript
function createPhoneNumber(numbers) {
  let str = numbers.join("");

  return `(${str.slice(0, 3)}) ${str.slice(3, 6)}-${str.slice(6, 10)}`;
}
```

</details>

<details><summary><b>Best solutions ✅</b></summary>

> Top ranked answer very clever 🔥. Imho:

```javascript
function createPhoneNumber(numbers) {
  var format = "(xxx) xxx-xxxx";

  for (var i = 0; i < numbers.length; i++) {
    format = format.replace("x", numbers[i]);
  }

  return format;
}
```

> 2nd ranked answer ✅. Similar to mine huh?

```javascript
function createPhoneNumber(numbers) {
  numbers = numbers.join("");
  return (
    "(" +
    numbers.substring(0, 3) +
    ") " +
    numbers.substring(3, 6) +
    "-" +
    numbers.substring(6)
  );
}
```

</details>

</details>

---

<details><summary><b>Day 8 (1)</b></summary>

#### Find The Parity Outlier

> 6 kyu

###### Description:

> You are given an array (which will have a length of at least 3, but could be very large) containing integers. The array is either entirely comprised of odd integers or entirely comprised of even integers except for a single integer `N`. Write a method that takes the array as an argument and returns this "outlier" `N`.

> Examples:

```javascript

[2, 4, 0, 100, 4, 11, 2602, 36]
Should return: 11 (the only odd number)

[160, 3, 1719, 19, 11, 13, -21]
Should return: 160 (the only even number)

```

<details><summary><b>My solution 😅</b></summary>

> tolerable 🥱

```javascript
function findOutlier(integers) {
  //your code here
  let arr1 = [];
  let arr2 = [];

  integers.filter((i) => (i % 2 === 0 ? arr1.push(i) : arr2.push(i)));

  return arr1.length > arr2.length ? arr2[0] : arr1[0];
}
```

</details>

<details><summary><b>Best solutions ✅</b></summary>

> Top ranked answer:

```javascript
function findOutlier(int) {
  var even = int.filter((a) => a % 2 == 0);
  var odd = int.filter((a) => a % 2 !== 0);
  return even.length == 1 ? even[0] : odd[0];
}
```

> 2nd ranked answer ✅

```javascript
function findOutlier(integers) {
  return integers.slice(0, 3).filter(even).length >= 2
    ? integers.find(odd)
    : integers.find(even);
}
function even(num) {
  return num % 2 == 0;
}
function odd(num) {
  return !even(num);
}
```

</details>

</details>

---

<details><summary><b>Day 8 (2)</b></summary>

#### Get the Middle Character

> 7 kyu

###### Description:

> You are going to be given a word. Your job is to return the middle character of the word. If the word's length is odd, return the middle character. If the word's length is even, return the middle 2 characters.

Examples:

```javascript
Kata.getMiddle("test") should return "es"

Kata.getMiddle("testing") should return "t"

Kata.getMiddle("middle") should return "dd"

Kata.getMiddle("A") should return "A"
```

<details><summary><b>My solution 😅</b></summary>

> tolerable 🥱

```javascript
function getMiddle(s) {
  let l = s.length;

  return l % 2 !== 0 ? s[l / 2 - 0.5] : `${s[l / 2 - 1]}${s[l / 2]}`;
}
```

</details>

<details><summary><b>Best solutions ✅</b></summary>

> Top ranked answer, meh...

```javascript
function getMiddle(s) {
  return s.substr(Math.ceil(s.length / 2 - 1), s.length % 2 === 0 ? 2 : 1);
}
```

> 2nd ranked answer ✅

```javascript
function getMiddle(s) {
  var middle = s.length / 2;
  return s.length % 2
    ? s.charAt(Math.floor(middle))
    : s.slice(middle - 1, middle + 1);
}
```

</details>

</details>

---

<details><summary><b>Day 8 (3)</b></summary>

#### Bit Counting

> 6 kyu

###### Description:

> Write a function that takes an integer as input, and returns the number of bits that are equal to one in the binary representation of that number. You can guarantee that input is non-negative.

Examples:

> The binary representation of `1234` is `10011010010`, so the function should return `5` in this case

<details><summary><b>My solution 😅</b></summary>

> Had no idea what binary was 🥲, but still...

```javascript
var countBits = function (n) {
  return n
    .toString(2)
    .split("")
    .filter((a) => a === "1").length;
};
```

</details>

<details><summary><b>Best solutions ✅</b></summary>

> Top ranked answer, one line 😬. Similar to mine, huh?

```javascript
countBits = (n) => n.toString(2).split("0").join("").length;
```

> 2nd ranked answer. I have no idea what is going on below 🤨

```javascript
function countBits(n) {
  for (c = 0; n; n >>= 1) c += n & 1;
  return c;
}
```

</details>

</details>

---

<details><summary><b>Day 9 (1)</b></summary>

#### Counting Duplicates

> 6 kyu

###### Description:

Count the number of Duplicates

> Write a function that will return the count of distinct case-insensitive alphabetic characters and numeric digits that occur more than once in the input string. The input string can be assumed to contain only alphabets (both uppercase and lowercase) and numeric digits.

Example:

> "abcde" -> 0 `# no characters repeats more than once`
> "aabbcde" -> 2 `# 'a' and 'b'`
> "aabBcde" -> 2 `# 'a' occurs twice and 'b' twice (`b`and`B`)`
> "indivisibility" -> 1 `# 'i' occurs six times`
> "Indivisibilities" -> 2 `# 'i' occurs seven times and 's' occurs twice`
> "aA11" -> 2 `# 'a' and '1'`
> "ABBA" -> 2 `# 'A' and 'B' each occur twice`

<details><summary><b>My solution 😅</b></summary>

```javascript
function duplicateCount(text) {
  let arr1 = text.toLowerCase().split("");
  let arr2 = [];
  arr1.filter((item, i) => {
    if (arr2.indexOf(item) === -1) {
      if (arr1.indexOf(item) !== i) {
        arr2.push(item);
      }
    }
    return arr2;
  });

  return arr2.length;
}
```

</details>

<details><summary><b>Best solutions ✅</b></summary>

> Top ranked answer 😐:

```javascript
function duplicateCount(text) {
  return (
    text
      .toLowerCase()
      .split("")
      .sort()
      .join("")
      .match(/([^])\1+/g) || []
  ).length;
}
```

> 2nd ranked answer ✅

```javascript
function duplicateCount(text) {
  return text
    .toLowerCase()
    .split("")
    .filter(function (val, i, arr) {
      return arr.indexOf(val) !== i && arr.lastIndexOf(val) === i;
    }).length;
}
```

</details>

</details>

---

<details><summary><b>Day 9 (2)</b></summary>

####

> 7 kyu

###### Description:

> An isogram is a word that has no repeating letters, consecutive or non-consecutive. Implement a function that determines whether a string that contains only letters is an isogram. Assume the empty string is an isogram. Ignore letter case.

Example: (Input --> Output)

```javascript
"Dermatoglyphics" --> true
"aba" --> false
"moOse" --> false (ignore letter case)
```

<details><summary><b>My solution 😅</b></summary>

```javascript
function isIsogram(str) {
  return (
    str
      .toLowerCase()
      .split("")
      .filter((item, pos, arr) => arr.indexOf(item) == pos).length == str.length
  );
}
```

</details>

<details><summary><b>Best solutions ✅</b></summary>

> Top ranked answer 😐:

```javascript
function isIsogram(str) {
  return !/(\w).*\1/i.test(str);
}
```

> 2nd ranked answer ✅

```javascript
function isIsogram(str) {
  return new Set(str.toUpperCase()).size == str.length;
}
```

</details>

</details>

---

<details><summary><b>Day 10 (1)</b></summary>

#### List Filtering

> 7 kyu

###### Description:

> In this kata you will create a function that takes a list of non-negative integers and strings and returns a new list with the strings filtered out.

Example:

```javascript
filter_list([1, 2, "a", "b"]) == [1, 2];
filter_list([1, "a", "b", 0, 15]) == [1, 0, 15];
filter_list([1, 2, "aasf", "1", "123", 123]) == [1, 2, 123];
```

<details><summary><b>My solution 😅</b></summary>

> I literally spent less than a minute 🥱

```javascript
function filter_list(l) {
  // Return a new array with the strings filtered out
  return l.filter((a) => typeof a === "number");
}
```

</details>

<details><summary><b>Best solutions ✅</b></summary>

> Top ranked answer 😐:

```javascript
function filter_list(l) {
  return l.filter(function (v) {
    return typeof v == "number";
  });
}
```

> 2nd ranked answer ✅

```javascript
function filter_list(l) {
  return l.filter((e) => Number.isInteger(e));
}
```

</details>

</details>

---

<details><summary><b>Day 10 (2)</b></summary>

#### Duplicate Encoder

> 6 kyu

###### Description:

> The goal of this exercise is to convert a string to a new string where each character in the new string is `"("` if that character appears only once in the original string, or `")"` if that character appears more than once in the original string. Ignore capitalization when determining if a character is a duplicate.

Example:

```javascript
"din"      =>  "((("
"recede"   =>  "()()()"
"Success"  =>  ")())())"
"(( @"     =>  "))(("
```

<details><summary><b>My solution 😅</b></summary>

> I..., I solved it 🥲

```javascript
function duplicateEncode(word) {
  let arr1 = word.toLowerCase().split("");
  let arr2 = [];

  arr1.filter((item, i) => {
    if (arr2.indexOf(item) === -1) {
      if (arr1.indexOf(item) !== i) {
        arr2.push(item);
      }
    }
    return arr2;
  });

  let arr3 = [];

  word
    .toLowerCase()
    .split("")
    .filter((a) => (arr2.includes(a) ? arr3.push(")") : arr3.push("(")));

  return arr3.join("");
}
```

</details>

<details><summary><b>Best solutions ✅</b></summary>

> Top ranked answer ✅:

```javascript
function duplicateEncode(word) {
  return word
    .toLowerCase()
    .split("")
    .map(function (a, i, w) {
      return w.indexOf(a) == w.lastIndexOf(a) ? "(" : ")";
    })
    .join("");
}
```

> 2nd ranked answer ✅

```javascript
function duplicateEncode(word) {
  word = word.toLowerCase();
  return word.replace(/./g, (m) =>
    word.indexOf(m) == word.lastIndexOf(m) ? "(" : ")"
  );
}
```

</details>

</details>

---

<details><summary><b>Day 11</b></summary>

#### Exes and Ohs

> 7 kyu

###### Description:

> Check to see if a string has the same amount of 'x's and 'o's. The method must return a boolean and be case insensitive. The string can contain any char.

Example:

```javascript
XO("ooxx") => true
XO("xooxx") => false
XO("ooxXm") => true
XO("zpzpzpp") => true // when no 'x' and 'o' is present should return true
XO("zzoo") => false
```

<details><summary><b>My solution 😅</b></summary>

> I... I solved it 😬. It should have been 6kyu Imho 🤨

```javascript
function XO(str) {
  let arr1 = [];
  let arr2 = [];

  str
    .toLowerCase()
    .split("")
    .map((a) => {
      if (a === "o") {
        arr1.push(a);
      }

      if (a === "x") {
        arr2.push(a);
      }
    });

  return arr1.length === arr2.length;
}
```

</details>

<details><summary><b>Best solutions ✅</b></summary>

> Top ranked answer ✅, f\*\*\* regex

```javascript
function XO(str) {
  let x = str.match(/x/gi);
  let o = str.match(/o/gi);
  return (x && x.length) === (o && o.length);
}
```

> 2nd ranked answer ✅, clever 🥲

```javascript
const XO = (str) => {
  str = str.toLowerCase().split("");
  return (
    str.filter((x) => x === "x").length === str.filter((x) => x === "o").length
  );
};
```

</details>

</details>

---

<details><summary><b>Day 12</b></summary>

#### Persistent Bugger.

> 6 kyu

###### Description:

> Write a function, `persistence`, that takes in a positive parameter `num` and returns its multiplicative persistence, which is the number of times you must multiply the digits in `num` until you reach a single digit.

For example (Input --> Output):

```javascript
39 --> 3 (because 3*9 = 27, 2*7 = 14, 1*4 = 4 and 4 has only one digit)
999 --> 4 (because 9*9*9 = 729, 7*2*9 = 126, 1*2*6 = 12, and finally 1*2 = 2)
4 --> 0 (because 4 is already a one-digit number)
```

<details><summary><b>My solution 😅</b></summary>

> Recursion baby, recursion 😅

```javascript
function persistence(num) {
  let counter = 1;
  function recurse(num) {
    let arr1 = num;
    let nums = 0;

    arr1 = arr1
      .toString()
      .split("")
      .map(Number)
      .reduce((a, b) => {
        return a * b;
      }, 1);

    if (arr1.toString().length !== 1) {
      return recurse(arr1, (counter += 1));
    } else {
      return counter;
    }
  }

  return num.toString().length === 1 ? 0 : recurse(num);
}
```

</details>

<details><summary><b>Best solutions ✅</b></summary>

> Top ranked answer ✅, meh 🥱:

```javascript
const persistence = (num) => {
  return `${num}`.length > 1
    ? 1 + persistence(`${num}`.split("").reduce((a, b) => a * +b))
    : 0;
};
```

> 2nd ranked answer ✅, clever 🥲

```javascript
function persistence(num) {
  var times = 0;

  num = num.toString();

  while (num.length > 1) {
    times++;
    num = num
      .split("")
      .map(Number)
      .reduce((a, b) => a * b)
      .toString();
  }

  return times;
}
```

</details>

</details>

---

<details><summary><b>Day 13</b></summary>

#### Tribonacci Sequence

> 6 kyu

###### Description:

> Well met with Fibonacci bigger brother, AKA Tribonacci.

> As the name may already reveal, it works basically like a Fibonacci, but summing the last 3 (instead of 2) numbers of the sequence to generate the next. And, worse part of it, regrettably I won't get to hear non-native Italian speakers trying to pronounce it :(

> So, if we are to start our Tribonacci sequence with `[1, 1, 1]` as a starting input (AKA signature), we have this sequence:

```javascript
[1, 1 ,1, 3, 5, 9, 17, 31, ...]
```

> But what if we started with [0, 0, 1] as a signature? As starting with [0, 1] instead of [1, 1] basically shifts the common Fibonacci sequence by once place, you may be tempted to think that we would get the same sequence shifted by 2 places, but that is not the case and we would get:

```javascript
[0, 0, 1, 1, 2, 4, 7, 13, 24, ...]
```

> Well, you may have guessed it by now, but to be clear: you need to create a fibonacci function that given a signature array/list, returns the first n elements - signature included of the so seeded sequence.

> Signature will always contain 3 numbers; n will always be a non-negative number; if n == 0, then return an empty array (except in C return NULL) and be ready for anything else which is not clearly specified ;)

<details><summary><b>My solution 😅</b></summary>

> While looop, recursion 😅

```javascript
function tribonacci(arr, time) {
  let arr1 = arr;
  let temp = 0;
  let times = time - 3;

  if (time === 0) {
    return [];
  } else if (time === 1) {
    return [arr[0]];
  }

  while (times >= 1) {
    temp = arr1.slice(-3)[0] + arr1.slice(-2)[0] + arr1.slice(-1)[0];

    arr1.push(temp);
    times--;
  }

  return arr1;
}
```

</details>

<details><summary><b>Best solutions ✅</b></summary>

> Top ranked answer 🥲:

```javascript
function tribonacci(signature, n) {
  for (var i = 0; i < n - 3; i++) {
    // iterate n times
    signature.push(signature[i] + signature[i + 1] + signature[i + 2]); // add last 3 array items and push to trib
  }
  return signature.slice(0, n); //return trib - length of n
}
```

> 2nd ranked answer ✅

```javascript
function tribonacci(signature, n) {
  const result = signature.slice(0, n);
  while (result.length < n) {
    result[result.length] = result.slice(-3).reduce((p, c) => p + c, 0);
  }
  return result;
}
```

</details>

</details>

---

<details><summary><b>Day 14</b></summary>

#### Friend or Foe?

> 6 kyu

###### Description:

> Make a program that filters a list of strings and returns a list with only your friends name in it.

> If a name has exactly 4 letters in it, you can be sure that it has to be a friend of yours! Otherwise, you can be sure he's not...

> Ex: Input = ["Ryan", "Kieran", "Jason", "Yous"], Output = ["Ryan", "Yous"]

Example:

```javascript
friend[("Ryan", "Kieran", "Mark")]`shouldBe`[("Ryan", "Mark")];
```

<details><summary><b>My solution, meh 🥱</b></summary>

> It wasn't a good fight for me

```javascript
function friend(friends) {
  return friends.filter((a) => a.length === 4 && a);
}
```

</details>

<details><summary><b>Best solutions ✅</b></summary>

> Top ranked answer (almost the same 😐):

```javascript
function friend(friends) {
  return friends.filter((n) => n.length === 4);
}
```

> 2nd ranked answer, meh 🥱

```javascript
const friend = (friends) => friends.filter((friend) => friend.length == 4);
```

</details>

</details>

---
