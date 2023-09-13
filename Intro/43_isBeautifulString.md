# isBeautifulString

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-10/PHSQhLEw3K2CmhhXE)

**Prompt:** A string is said to be beautiful if each letter in the string appears at most as many times as the previous letter in the alphabet within the string; ie: b occurs no more times than a; c occurs no more times than b; etc. Note that letter a has no previous letter.

Given a string, check whether it is beautiful.

**Initial Thoughts:**

```
// I think we can sort the array, then as we're looping through the array we can check that the current charCode is no more than 1 greater than the previous charCode. This ensures we're not skipping any letters.

// At the same time, we'll count the consecutive characters and previous consecutive characters to ensure that current consecutive characters is never larger than previous consecutive characters.

// If either of the previous conditions occur, we know to return false. Otherwise if we make it to the end of the array without either occuring we can return true.
```

**Solution:**

```
function solution(inputString) {
  const sortedString = inputString.split("").sort().join("");
  let currentCharCode = sortedString.charCodeAt(0);
  let consecutiveSameCharacter = 0;
  let prevConsecutiveSameCharacter = 0;
  for (let i = 0; i < sortedString.length; i++) {
    consecutiveSameCharacter++;
    if (sortedString.charCodeAt(i) > currentCharCode + 1) {
      return false;
    } else if (sortedString.charCodeAt(i) === currentCharCode + 1) {
      currentCharCode++;
      prevConsecutiveSameCharacter = consecutiveSameCharacter - 1;
      consecutiveSameCharacter = 1;
    } else if (
      consecutiveSameCharacter > prevConsecutiveSameCharacter &&
      sortedString[i] !== "a"
    ) {
      return false;
    }
  }
  return true;
}
```

**Reflection:** My general logic was ok, I just got caught up in a little bit of messiness as I was writing the code out.

One cool thing I learned while doing this problem is that we can use the `.split()` method to indirectly count how many times a word or character appears in a string, and by doing that we can write a much cleaner solution to this problem:

```
function solution(inputString) {
  s = "abcdefghijklmnopqrstuvwxyz";
  for (i = 1; i < s.length; i++) {
    if (
      inputString.split(s[i]).length - 1 >
      inputString.split(s[i - 1]).length - 1
    ) {
      return false;
    }
  }
  return true;
}
```
