# absoluteValuesSumMinimization

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-7/ZFnQkq9RmMiyE6qtq)

**Prompt:** Given a sorted array of integers a, your task is to determine which element of a is closest to all other values of a. In other words, find the element x in a, which minimizes the following sum:

abs(a[0] - x) + abs(a[1] - x) + ... + abs(a[a.length - 1] - x)
(where abs denotes the absolute value)

If there are several possible answers, output the smallest one.

**Initial Thoughts:**

```
// I think I can loop through the array and at each index pass a callback to the reduce function to calculate the currentAbsoluteSum.

// Then, if the currentAbsoluteSum is smaller than minimalAbsoluteSum, I can set minimalAbsoluteSum to currentAbsoluteSum and also update result.

// After I finish looping through all of the array items I simply need to return result.
```

**Solution:**

```function solution(a) {
  let result;
  let minimalAbsoluteSum;

  for (let i = 0; i < a.length; i++) {
    const currentAbsoluteSum = a.reduce(
      (acc, b) => acc + Math.abs(b - a[i]),
      0
    );
    if (currentAbsoluteSum < minimalAbsoluteSum || !minimalAbsoluteSum) {
      minimalAbsoluteSum = currentAbsoluteSum;
      result = a[i];
    }
  }
  return result;
}
```

**Reflection:** While my approach was valid, apparently the simpler solution was to simply find the median value in the array and return that.

While my intuition clearly didn't lead me in that direction, In hindsight I can see how this could be a valid and more concise, performant solution:

```
function solution(A) {
    return A[Math.ceil(A.length/2)-1];
}
```
