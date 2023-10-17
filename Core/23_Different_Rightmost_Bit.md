# Different Rightmost Bit

[**Challenge Link**](https://app.codesignal.com/arcade/code-arcade/corner-of-0s-and-1s/whz5JzszYTdXW6aNA)

**Prompt:** You're given two integers, n and m. Find position of the rightmost bit in which they differ in their binary representations (it is guaranteed that such a bit exists), counting from right to left.

Return the value of 2position_of_the_found_bit (0-based).

**Initial Thoughts:**

```

// So it looks like step 1 is we need to convert 'n' and 'm' into binary strings.

// Then, we loop through both strings comparing the differences, and for the final difference we do 2 the power of string length minus the index where the final difference occured.

// Update: My solution didn’t work because CodeSignal doesn’t allow for updating their boilerplate code so we had to use bitwise operators instead.

```

**My Solution:**

```
function solution(n, m) {
  return (n ^ m) & -(n ^ m);
}
```

**Reflection:** The way the solution works is we use an XOR (^) operator to return 1s in each position n and m are different.

Then we negate the differences inside `-(n ^ m)` and by combining the results we can get our answer.

I had to consult the bitwise operator documentation to solve this problem and I still don't feel very comfortable with bitwise operators, but I'm just trying to get a high level exposure to them in this section.
