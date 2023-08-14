# checkPalindrome

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-1/s5PbmwxfECC52PWyQ)

**Prompt:** Given the string, check if it is a palindrome.

**Solution:**

```
function solution(inputString) {
    return inputString == inputString.split('').reverse().join('');
}
```

**Reflection:** I came up with what seems to be pretty much the ideal solution after a couple minutes. Not much to improve here.
