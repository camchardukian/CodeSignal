# Circle of Numbers

[**Challenge Link**](https://app.codesignal.com/arcade/code-arcade/intro-gates/vExYvcGnFsEYSt8nQ)

**Prompt:** Consider integer numbers from 0 to n - 1 written down along the circle in such a way that the distance between any two neighboring numbers is equal (note that 0 and n - 1 are neighboring, too).

Given n and firstNumber, find the number which is written in the radially opposite position to firstNumber.

**Initial Thoughts:**

```
// This problem seems pretty simple. At its core, we have two numbers separated by half a circle.

// We can take half of the circle which is n / 2. If firstNumber is greater than n / 2, our answer is firstNumber + half of n.

// Otherwise our answer is firstNumber - half of n.
```

**My Solution:**

```
function solution(n, firstNumber) {
  const half = n / 2;
  return firstNumber < half ? firstNumber + half : firstNumber - half;
}
```

**Reflection:** I saw there was a slightly more clever answer than mine in the comments that used the modulo operator:

```
function solution(n, firstNumber) {
  return (firstNumber + n / 2) % n;
}
```

With that being said, my solution wasn't bad. Anyway, I noted this potential optimization for if I encounter a similar problem in the future and will be ready for it.
