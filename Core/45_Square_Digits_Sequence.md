# Square Digits Sequence

[**Challenge Link**](https://app.codesignal.com/arcade/code-arcade/labyrinth-of-nested-loops/MvX84CA5HN6GKqv7R)

**Prompt:** Consider a sequence of numbers a0, a1, ..., an, in which an element is equal to the sum of squared digits of the previous element. The sequence ends once an element that has already been in the sequence appears again.

Given the first element a0, find the length of the sequence.

**Initial Thoughts:**

```
// The first step is we need a reusable function that will take all of the digits in a given number and add their squares.

// Then we will use a while loop that continues while true and checks if numbersSeqeuence includes the current result of sumSquaresOfDigits.

// If so, we return numbersSeqeuence.length + 1. If not, we push said sum to numbersSequence.
```

**My Solution:**

```
function sumSquaresOfDigits(number) {
  return number
    .toString()
    .split("")
    .map((item) => parseInt(item))
    .reduce((a, b) => a + Math.pow(b, 2), 0);
}

function solution(a0) {
  let currentNumber = a0;
  const numbersSequence = [currentNumber];
  while (true) {
    if (numbersSequence.includes(sumSquaresOfDigits(currentNumber))) {
      return numbersSequence.length + 1;
    }
    currentNumber = sumSquaresOfDigits(currentNumber);
    numbersSequence.push(currentNumber);
  }
}

```

**Reflection:** My solution aimed to be more readable than others via usage of a separate helper function `sumSquaresOfDigits()`.
