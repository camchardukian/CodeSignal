# Kill K-th Bit

[**Challenge Link**](https://app.codesignal.com/arcade/code-arcade/corner-of-0s-and-1s/b5z4P2r2CGCtf8HCR)

**Prompt:** Implement the missing code, denoted by ellipses. You may not modify the pre-existing code.
In order to stop the Mad Coder evil genius you need to decipher the encrypted message he sent to his minions. The message contains several numbers that, when typed into a supercomputer, will launch a missile into the sky blocking out the sun, and making all the people on Earth grumpy and sad.

You figured out that some numbers have a modified single digit in their binary representation. More specifically, in the given number n the kth bit from the right was initially set to 0, but its current value might be different. It's now up to you to write a function that will change the kth bit of n back to 0.

**Initial Thoughts:**

```
// Seems like what we need to do is first get the binary representation of n. Then, we need to replace the integer at position k of the binary representation with a 0.

// Finally, we need to convert the modified binary back into a standard integer.
```

**My Solution:**

```
function solution(n, k) {
  return parseInt(
    n.toString(2).substring(0, n.toString(2).length - k) +
      "0" +
      n.toString(2).substring(n.toString(2).length - k + 1),
    2
  );
}
```

**Reflection:** This problem was tough. It took me a pretty long time to get a working solution, my first attempt (shown below) was close but failed some cases:

```
function solution(n, k) {
  return parseInt(
    n.toString(2).substring(0, k) + "0" + n.toString(2).substring(k + 1),
    2
  );
}
```

I now see that this problem was trying to test our knowledge of bitwise operators, something I don't have a whole lot of experience in. The elegant solution to this problem actually looks like this:

```
function solution(n, k) {
  return n & ~(1 << (k - 1));
}
```
