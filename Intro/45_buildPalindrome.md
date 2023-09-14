# buildPalindrome

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-10/ppZ9zSufpjyzAsSEx)

**Prompt:** Given a string, find the shortest possible string which can be achieved by adding characters to the end of initial string to make it a palindrome.

**Initial Thoughts:**

```
// If the string is already a palindrome, we just return the string.

// Otherwise, we have to turn the string into a palindrome. How can we do that? Hmm... I'm having trouble figuring out how to do this without knowing how long the final string will be.

// Could we just add the first character of our initial string to the end of the string and check if it's a palindrome? If so, return it. Otherwise, add the 2nd character of our string at the finalString.length - 2 index, and repeat this process until we have a palindrome?
```

**Solution:**

```
function solution(st) {
  const isPalindrome = (string) => {
    return string === string.split("").reverse().join("");
  };
  if (isPalindrome(st)) {
    return st;
  }
  let modifiedString = st;
  for (let i = 0; i < st.length; i++) {
    modifiedString =
      modifiedString.slice(0, modifiedString.length - i) +
      modifiedString[i] +
      modifiedString.slice(modifiedString.length - i);
    if (isPalindrome(modifiedString)) {
      return modifiedString;
    }
  }
}
```

**Reflection:** I'm proud of myself for initially having no idea about how to solve this problem, but then taking a deep breath and then after a few minutes coming up with some pseudocode for how we might tackle this problem.

It just so turns out that my solution was pretty similar to the other top voted community submissions. Cool. On to the next problem.
