# longestWord

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-12/s9qvXv4yTaWg8g4ma)

**Prompt:** Define a word as a sequence of consecutive English letters. Find the longest word from the given string.

Example

For text = "Ready, steady, go!", the output should be
solution(text) = "steady".

**Initial Thoughts:**

```
// I'm pretty sure this was similar to the regex we used a few problems back for checking if we had multiple of the same letter in a row.

// We just try to check how long the longest consecutive number of letters there are in a row before another character.
```

**My Solution:**

```
function solution(text) {
  const regex = /[A-Za-z]+/g;
  const results = text.match(regex);
  return results.sort((a, b) => b.length - a.length)[0];
}
```

**Reflection:** This problem was similar to sorting an array of numbers from smallest to largest or largest to smallest. The only difference was that we had to get the length of the words in the string, and identify what constituted a 'word'.

Overall, this problem was fairly straightforward and I was able to come up with a pretty optimal solution after several minutes.
