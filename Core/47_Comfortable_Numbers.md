# Comfortable Numbers

[**Challenge Link**](https://app.codesignal.com/arcade/code-arcade/labyrinth-of-nested-loops/pNfGgNk46YZ4c4RW5)

**Prompt:** Let's say that number a feels comfortable with number b if a ≠ b and b lies in the segment [a - s(a), a + s(a)], where s(x) is the sum of x's digits.

How many pairs (a, b) are there, such that a < b, both a and b lie on the segment [l, r], and each number feels comfortable with the other (so a feels comfortable with b and b feels comfortable with a)?

**Initial Thoughts:**

```
// First, we need to create a dictionary for which numbers are comfortable with which other numbers.

// To do this, we need to sum up the digits within a number and then loop from i - digitsSum to i + digitsSum, pushing all of the values into an array. Then we can assign that array to the dictionary[i].

// Then, we can use nested loops. The outer loop will iterate between each number, and the inner loop will iterate between each item's numbers to see if those numbers also feel comfortable.

// Update: I'm using way too many loops which causes me to timeout if our inputs l and r are sufficiently far apart.
```

**My Solution:**

```
function sumDigitsOfNumber(n) {
  let sum = 0;
  while (n) {
    sum += n % 10;
    n = Math.floor(n / 10);
  }
  return sum;
}

function solution(l, r) {
  let count = 0;
  for (let i = l; i <= r; i++) {
    for (let ii = i + 1; ii <= r; ii++) {
      if (i + sumDigitsOfNumber(i) >= ii && ii - sumDigitsOfNumber(ii) <= i) {
        count++;
      }
    }
  }
  return count;
}
```

**Reflection:** I ended up having to reference the community submissions for help as I found this problem to be just too difficult to understand. With an almost 90% thumbs down percentage, I'm not the only one to have problems with this problem but nonetheless it's still disappointing whenever you're not able to solve a problem entirely on your own.
