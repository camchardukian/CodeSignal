# Weak Numbers

[**Challenge Link**](https://app.codesignal.com/arcade/code-arcade/labyrinth-of-nested-loops/oL7YuygJKtMSNLeJn)

**Prompt:** We define the weakness of number x as the number of positive integers smaller than x that have more divisors than x.

It follows that the weaker the number, the greater overall weakness it has. For the given integer n, you need to answer two questions:

what is the weakness of the weakest numbers in the range [1, n]?
how many numbers in the range [1, n] have this weakness?
Return the answer as an array of two elements, where the first element is the answer to the first question, and the second element is the answer to the second question.

**Initial Thoughts:**

```
// We can loop from 1 to n to get the number of divisors for each number, and push it to a divisorsCountArray.

// Then, we will loop again, and this time use a slice from 0 to i - 1 to see the weakness of each number, and push the result to a weaknesses array.

// Finally, we'll use the Math.max() function to get the largest number of weaknesses, and filter the weaknesses array to see how many numbers have said number of weaknesses.

// We can then return the result as something like:[largestWeakness, largestWeaknessCount]
```

**My Solution:**

```
function getDivisors(number) {
  let divisorsArray = [];
  for (let i = 1; i <= number; i++) {
    let divisors = 0;
    for (let ii = 1; ii <= i; ii++) {
      if (!(i % ii)) {
        divisors += 1;
      }
    }
    divisorsArray.push(divisors);
  }
  return divisorsArray;
}

function getWeaknesses(divisors) {
  const weaknessesArray = [];
  for (let i = 0; i < divisors.length; i++) {
    let currentWeakness = 0;
    if (i === 0) {
      weaknessesArray.push(currentWeakness);
      continue;
    }
    const prevDivisors = divisors.slice(0, i);
    for (let ii = 0; ii < prevDivisors.length; ii++) {
      if (prevDivisors[ii] > divisors[i]) {
        currentWeakness++;
      }
    }
    weaknessesArray.push(currentWeakness);
  }
  return weaknessesArray;
}

function solution(n) {
  const divisors = getDivisors(n);
  const weaknesses = getWeaknesses(divisors);
  const largestWeakness = Math.max(...weaknesses);
  const largestWeaknessCount = weaknesses.filter(
    (item) => item === largestWeakness
  ).length;

  return [largestWeakness, largestWeaknessCount];
}
```

**Reflection:** This problem was quite tedious. My solution is far more readable than the others (in my somewhat less than humble opinion), but I would've liked to have been able to solve this problem with less usage of nested loops.
