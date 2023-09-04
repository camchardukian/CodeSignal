# Array Replace

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-6/mCkmbxdMsMTjBc3Bm)

**Prompt:** Given an array of integers, replace all the occurrences of elemToReplace with substitutionElem.

**Initial thoughts:**

```
// This problem seems simple. One approach would be to simply loop through the input array and if the value at a given index was elemToReplace, we'd set the value at that index to substitutionElem.

// Another approach we could take would be to to convert the inputArray to a string, and then run replaceAll() on the string, and then join() the string back into an array, but then we'd have to perform at least one other operation to coerce those number strings back into integers.

// For that reason, I think the best approach is going to be the simple for loop.
```

**Solution:**

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

**Reflection:** My approach worked and was fairly efficient, but it completely overlooked that we could have used the built in `.map()` method to be more concise and readable for other developers.

This was literally the perfect use case for mapping, so it's a little disappointing I ran back to the good old for loop to solve this problem.

Maybe it's poor sleep last night, or further pattern recognition skill improvements needed.

Either way, I'll continue to keep improving!
