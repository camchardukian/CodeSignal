# Circle of Numbers

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-7/vExYvcGnFsEYSt8nQ)

**Prompt:** Consider integer numbers from 0 to n - 1 written down along the circle in such a way that the distance between any two neighboring numbers is equal (note that 0 and n - 1 are neighboring, too).

Given n and firstNumber, find the number which is written in the radially opposite position to firstNumber.

**Initial Thoughts:**

```
// It seems like if a number is opposite of another number, that means the numbers must be separated by half of the total number of integers.

// For example if n is the total number of integers, and firstNumber is 2, we calculate the number opposite of 2 by doing 2 + (n / 2).

// Of course, there could be a case where firstNumber is larger than 1/2 of n. In that case, we need to subtract.
```

**Solution:**

```
function solution(n, firstNumber) {
  const half = n / 2;
  return firstNumber < half ? firstNumber + half : firstNumber - half;
}
```

**Reflection:** My solution worked fine, was performant, and readable. There was an alternative approach to the problem, however, where you could calculate the solution via the remainder:

```
function solution(n, firstNumber) {
  return (n/2+firstNumber)%n
}
```

Both solutions are valid, with minimal differences in their conciseness and readability.
