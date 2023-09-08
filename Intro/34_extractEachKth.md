# extractEachKth

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-8/3AgqcKrxbwFhd3Z3R)

**Prompt:** Given array of integers, remove each kth element from it.

**Initial Thoughts:**

```
// This seems like we just need to loop through the array starting at the k - 1 index, splice, increment the loop iterator by k, and repeat. After looping through everything we should be able to return inputArray.

// Note: After I started implementing the problem I realized we have to increment by k - 1 instead of incrementing by only k. The reason for this is because we're removing an element from the array with splice.
```

**Solution:**

```
function solution(inputArray, k) {
  for (let i = k - 1; i < inputArray.length; i += k - 1) {
    inputArray.splice(i, 1);
  }
  return inputArray;
}
```

**Reflection:** My solution wasn't bad, but I forgot to consider that using the filter method may have been a more straightforward solution given that that the purpose of that method is literally to remove elements from an array.
