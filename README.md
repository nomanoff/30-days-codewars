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

<details><summary><b>Day 6</b></summary>

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
