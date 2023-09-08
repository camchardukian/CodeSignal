# differentSymbolsNaive

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-8/8N7p3MqzGQg5vFJfZ)

**Prompt:** Given a string, find the number of different characters in it.

**Initial Thoughts:**

```
// I think we can loop through the string, increment count, and replace every new character globally as we encounter them to prevent ourselves from counting a letter more than once.
```

**Solution:**

```
function solution(s) {
  let uniqueCharacterCount = 0;
  let replaceString = s;
  for (let i = 0; i < s.length; i++) {
    if (replaceString[i] !== "#") {
      uniqueCharacterCount++;
      replaceString = replaceString.replaceAll(replaceString[i], "#");
    }
  }
  return uniqueCharacterCount;
}
```

**Reflection:** It seems there was a far simpler solution to this problem -- the usage of JavaScript `Sets`.

The ideal solution to this problem would have looked something like this:

```
function solution(s) {
    return new Set(s).size
}
```
