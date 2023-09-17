# lineEncoding

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-11/o2uq6eTuvk7atGadR)

**Prompt:** Given a string, return its encoding defined as follows:

First, the string is divided into the least possible number of disjoint substrings consisting of identical characters
for example, "aabbbc" is divided into ["aa", "bbb", "c"]
Next, each substring with length greater than one is replaced with a concatenation of its length and the repeating character
for example, substring "bbb" is replaced by "3b"
Finally, all the new strings are concatenated together in the same order and a new string is returned.

**Initial Thoughts:**

```
// I think the obvious solution here is to loop through the entire string, and maintain an increment count of how many times the current character has been repeated, and then push that character along with the increment count to a new array whenever there is a new character.

// Finally, at the end we can return the joined array as our solution.
```

**Solution:**

```
function solution(s) {
  let countOfCharacter = 1;
  let currentCharacter = s[0];
  let characterArray = [];
  for (let i = 0; i < s.length + 1; i++) {
    if (!i) {
      continue;
    } else if (s[i] === s[i - 1]) {
      countOfCharacter++;
      continue;
    }
    characterArray.push(
      `${countOfCharacter > 1 ? countOfCharacter : ""}${currentCharacter}`
    );
    currentCharacter = s[i];
    countOfCharacter = 1;
  }
  return characterArray.join("");
}
```

**Reflection:** In the end, I was able to come up with a decent solution. I was impressed to discover that instead of my fairly complex solution (in comparison), it was actually possible to solve this problem with regex:

```

solution = s =>
    s.replace(
        /(.)\1*/g,
        (e,i) => i==e ? i : e.length+i
    )
```
