# arrayMaxConsecutiveSum

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-8/Rqvw3daffNE7sT7d5)

**Prompt:** Given array of integers, find the maximal possible sum of some of its k consecutive elements.

**Initial Thoughts:**

```
// I think we can solve this problem by looping through the array starting at index k - 1, and then we sum up i and the preceding k elements - 1.

// We then keep doing this each time and check if the currentSum is larger than largestSum, and if so, we set largestSum to currentSum.

// After we loop through all of the array items, we return largestSum.
```

**Solution:**

```
function solution(inputArray, k) {
  let maximumLargestSum = inputArray.slice(0, k).reduce((a, b) => a + b);
  let currentMaximumSum = maximumLargestSum;
  for (let i = 0; i < inputArray.length; i++) {
    currentMaximumSum -= inputArray[i];
    currentMaximumSum += inputArray[i + k];
    if (currentMaximumSum > maximumLargestSum) {
      maximumLargestSum = currentMaximumSum;
    }
  }
  return maximumLargestSum;
}
```

**Reflection:** I was able to solve this problem using a for loop:

```
function solution(inputArray, k) {
    let largestSum = 0;
    for (let i = k - 1; i < inputArray.length; i++) {
    const currentSum = inputArray.slice(i - k + 1, i + 1).reduce((a, b) => a + b);
        if (currentSum > largestSum) {
        largestSum = currentSum;
        }
    }
    return largestSum;
}
```

Unfortunately, my first solution only passed 19 out of 20 test cases (because it was too slow, probably because I was having to call reduce with each iteration of the loop).

The good thing, however, is this forced me to look for a more optimal solution. I'd heard of sliding windows, but never implemented them before.

The name sliding window sounded like it may fit this algorithm, and when I took the time to search _sliding window_, figure out what it is, and how it works, it turned out to be a perfect use case of that algorithm.

Solving this problem and learning about sliding windows gave me a lot more confidence in my dsa abilities.

I'm confident that if I keep putting in the time and exposing myself to new concepts that I can master dsa.
