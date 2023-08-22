# commonCharacterCount

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-3/JKKuHJknZNj4YGL32)

**Prompt:** Given two strings, find the number of common characters between them.

**Pseudocode:**

```
// We know the strings will be English lowercase characters and that it's possible the two strings will be different lengths. For that reason we need to first find which string is shorter.

// Once we've identified the string with the shorter length, we then loop through the short string.

// Then, for each letter we check if the indexOf said letter versus the longer string

// We also need to replace/remove using splice/slice once a given letter has been matched so that we don't let an individual letter from the long string be matched multiple times.
```

**Solution:**

```
function solution(s1, s2) {
  let longString = s1.length >= s2.length ? s1 : s2;
  let shortString = s1.length >= s2.length ? s2 : s1;
  let commonCharacters = 0;
  for (let i = 0; i < shortString.length; i += 1) {
    const indexOfResult = longString.indexOf(shortString[i]);
    if (indexOfResult > -1) {
      commonCharacters += 1;
      longString =
        longString.slice(0, indexOfResult) +
        longString.slice(indexOfResult + 1);
    }
  }
  return commonCharacters;
}
```

**Reflection:** My solution worked ok, but after solving the problem I looked at other solutions and realized I could have made this solution much more simple and concise by simply looping through one string and using the replace method to add some dummy character like "$", and afterwards just count all of the "$" characters.
