# digitDegree

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-9/hoLtYWbjdrD2PF6yo)

**Prompt:** Let's define digit degree of some positive integer as the number of times we need to replace this number with the sum of its digits until we get to a one digit number.

Given an integer, find its digit degree.

**Initial Thoughts:**

```
// We can turn `n` into a string, and then split it into an array.

// I'm thinking that we can do a while loop, and while our variable isOneDigitNumber is false, we keep looping.

// Each time we loop through the array we use the reduce method on all of the items to add the integers, then we check if the result is less than 10.

// If less than 10, we set isOneDigitNumber to true, break out of the loop, and return the digitDegree, if more than 10, we increment digitDegree.
```

**Solution:**

```
function solution(n) {
  let integerArray = n.toString().split("");
  let numberOfIterations = 0;
  if (integerArray.length > 1) {
    while (true) {
      numberOfIterations++;
      const result = integerArray.reduce((a, b) => parseInt(a) + parseInt(b));
      if (result < 10) {
        return numberOfIterations;
      }
      integerArray = result.toString().split("");
    }
  }
  return numberOfIterations;
}
```

**Reflection:** It seems like my general logic was on point. I could've made my solution a bit more concise, like this one:

```
function solution(n) {
  c = 0;
  while (n.toString().length > 1) {
    n = n
      .toString()
      .split("")
      .reduce((x, y) => Number(x) + Number(y));
    c++;
  }
  return c;
}
```

The key was that instead of separating the if statement and while loop conditions, I could've combined them into one. I also could've removed the need for a separate `result` variable.

Overall, however, we did a mostly good job with this problem.
