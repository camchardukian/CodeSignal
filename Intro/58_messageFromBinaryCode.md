# messageFromBinaryCode

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-12/sCpwzJCyBy2tDSxKW)

**Prompt:** You are taking part in an Escape Room challenge designed specifically for programmers. In your efforts to find a clue, you've found a binary code written on the wall behind a vase, and realized that it must be an encrypted message. After some thought, your first guess is that each consecutive 8 bits of the code stand for the character with the corresponding extended ASCII code.

Assuming that your hunch is correct, decode the message.

**Initial Thoughts:**

```
// The first thing I need to do is understand the binary numeral system and the rules for calculating what number is the result of each 8 character binary string.

// After reviewing some mdn documentation, I found that I don't need to manually calculate this. I can use the parseInt method and set the radix to 2.

// Once I get the output of 72, I can use String.fromCharCode() to get "H".

// So, I think I can loop through the given code string, increment by 8, and each time concat the result to my output string.
```

**My Solution:**

```
function solution(code) {
  let decodedMessage = "";
  for (let i = 0; i < code.length; i += 8) {
    decodedMessage += String.fromCharCode(
      parseInt(code.substring(i, i + 8), 2)
    );
  }
  return decodedMessage;
}
```

**Reflection:** I learned a couple cool things while working on this problem. One, I finally somewhat understand the `radix` parameter of the `parseInt()` method.

I also developed a better understanding of string manipulation by learning that `+=` is for modifying and building strings in-place whereas `concat()` is for creating a new string without modifying the original strings.

As far as optimal solutions are concerned, I saw other answers use regex matching plus a reduce method instead of looping.

I think those answers may be slightly more efficient than mine, and I'll try to keep them in mind the next time I encounter a similar problem.
