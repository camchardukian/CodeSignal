# Mirror Bits

[**Challenge Link**](https://app.codesignal.com/arcade/code-arcade/corner-of-0s-and-1s/e3zfPNTwTa9qTQzcX)

**Prompt:** Reverse the order of the bits in a given integer.

**Initial Thoughts:**

```
// I think there's a bitwise operator to solve this problem. I think it's the ~ bitwise operator. I think we can return 'a' with the ~ operator for our answer.

// If we need to do things more manually, however, we could turn 'a' into a binary string, reverse the string, and then use parseInt to turn it back into a number to return.

// Update: The ~ bitwise operator is used to invert, not reverse. For that reason, I had to follow my second idea.
```

**My Solution:**

```
function solution(a) {
  return parseInt(a.toString(2).split("").reverse().join(""), 2);
}
```

**Reflection:** My solution was pretty close to the most upvoted community submission. The only difference was their top submission used the spread operator to form an array in one step rather than having an additional split operation like I did:

```
function solution(a) {
  return parseInt([...a.toString(2)].reverse().join(""), 2);
}
```
