# Second-Rightmost Zero Bit

[**Challenge Link**](https://app.codesignal.com/arcade/code-arcade/corner-of-0s-and-1s/9nSj6DgqLDsBePJha)

**Prompt:** Implement the missing code, denoted by ellipses. You may not modify the pre-existing code.
Presented with the integer n, find the 0-based position of the second rightmost zero bit in its binary representation (it is guaranteed that such a bit exists), counting from right to left.

Return the value of 2position_of_the_found_bit.

Example:

For n = 37, the output should be
solution(n) = 8.

3710 = 1001012. The second rightmost zero bit is at position 3 (0-based) from the right in the binary representation of n.
Thus, the answer is 23 = 8.

**Initial Thoughts:**

```
// Honestly, I just don't clearly understand this question. I thought I needed to convert the 'n' integer to a binary string, and then find the 2nd to last occurence of zero within the string, but then I'd expect to return 5 rather than 8 in the example case.

// For that reason, I don't think I'm understanding clearly what this question is asking of me.

// One cool thing I learned while trying to solve this problem is that the .split() method in JS has a 2nd optional parameter (limit).
```

**My Solution:**

```
function solution(n) {
  return Math.pow(
    n.toString(2).split("").reverse().join().split("0", 2).length,
    2
  );
}
```

**Reflection:** I'm not sure how much of my difficulty solving this problem was incorrect assumptions and knowledge gaps and how much of it was the question being poorly worded.

In the end, I was able to get semi-close to a solution but ended up having to peek at other submissions in order to solve the problem. :\(

```
function solution(n) {
  return Math.pow(
    2,
    n.toString(2).split("").reverse().join("").split("0", 2).join("0").length
  );
}
```

I wasn't that far off, but of course it's always disappointing when you're not able to get across the finish line without help.

Oh well, we'll regroup and try again tomorrow. I'm excited to finish these bitwise problems over the next couple days and get back to DSA topics more commonly asked by tech companies.
