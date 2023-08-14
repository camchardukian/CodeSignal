# adjacentElementsProduct

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-2/xzKiBHjhoinnpdh6m)

**Prompt:** Given an array of integers, find the pair of adjacent elements that has the largest product and return that product.

**Solution:**

```
function solution(inputArray) {
    let currentLargestIndexes = [0, 1];
    for (let i = 1; i < inputArray.length - 1; i+=1) {
        if (inputArray[i] * inputArray[i + 1] > inputArray[currentLargestIndexes[0]] * inputArray[currentLargestIndexes[1]]) {
            currentLargestIndexes = [i, i + 1]
        }
    }
    return inputArray[currentLargestIndexes[0]] * inputArray[currentLargestIndexes[1]];
}
```

**Reflection:** I saw another solution that was more concise due to the usage of the `Math.max()` operator, but that code didn't read as clearly to me so I'm satisfied with my solution for this problem.
