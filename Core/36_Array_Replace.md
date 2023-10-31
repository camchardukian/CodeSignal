# Array Replace

[**Challenge Link**](https://app.codesignal.com/arcade/code-arcade/list-forest-edge/mCkmbxdMsMTjBc3Bm)

**Prompt:** Given an array of integers, replace all the occurrences of elemToReplace with substitutionElem.

**Initial Thoughts:**

```
// There's a couple ways to solve this problem. First we could loop through the array and manually replace things.

// Maybe we could also join all elements in the array, and do a global replace, but I think that approach is riskier.
```

**My Solution:**

```
function solution(inputArray, elemToReplace, substitutionElem) {
  for (let i = 0; i < inputArray.length; i++) {
    if (inputArray[i] === elemToReplace) {
      inputArray[i] = substitutionElem;
    }
  }
  return inputArray;
}
```

**Reflection:** Oh man, I can't believe I overlooked the _.map()_ function here. This is a textbook problem of what that function was intended for.

I guess my brain is still waking up this morning...
