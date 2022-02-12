<div align="center">
  <img height="60" src="./assets/codewars_button_icon.png">
  <h1>30 Days Codewars</h1>

---

<span>Hello 🌏! I like solving coding problems, especially on <a href="https://www.codewars.com/">codewars</a>. So, I decided to share my 30-days-of-solving-codewars-problems journey here.</span>

<span>Everyday I will solve one question from codewars and share below. It will include the question, my answer and one or two best answers from the codewars community.</span>

Ways to reach out to me 👇 <br />
<a target="_blank" href="https://twitter.com/nomanoff_tech">Twitter</a> || <a href="https://www.linkedin.com/in/me-adam/">LinkedIn</a> || <a href="https://dev.to/nomanoff_tech">Blogs</a>

> Btw, if you find some typos, feel free to leave a PR 😎

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

```

</details>

<details><summary><b>Best Answers ✅</b></summary>

> Top ranked answer:

```javascript

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
