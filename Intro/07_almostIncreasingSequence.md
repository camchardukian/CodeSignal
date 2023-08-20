# almostIncreasingSequence

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-2/2mxbGwLzvkTCKAJMG)

**Prompt:** Given a sequence of integers as an array, determine whether it is possible to obtain a strictly increasing sequence by removing no more than one element from the array.

Note: sequence a0, a1, ..., an is considered to be a strictly increasing if a0 < a1 < ... < an. Sequence containing only one element is also considered to be strictly increasing.

**Solution:**

```
function solution(sequence) {
  let itemToRemoveCount = 0;
  for (let i = 1; i < sequence.length; i += 1) {
    if (sequence[i] <= sequence[i - 1]) {
      itemToRemoveCount +=1
    if (itemToRemoveCount > 1) {
      return false;
    }
      if (sequence[i] <= sequence[i - 2] && i < sequence.length - 1 && sequence[i + 1] <= sequence[i - 1]) {
        return false;
      }
    }
  }
  return true;
}
```

**Reflection:** This was far and away the most difficult problem thus far. Not only was the algorithm fairly complex due to the many edge cases, I'd also overlooked that CodeSignal's definition of a strictly increasing sequence couldn't include duplicates.

In other words, if the final result was [1, 2, 2, 3] I needed to return false because the value at index 2 (2) was equal to, and not larger than the value at index 1 (2).

It just goes to show the value in writing pseudocode and trying to think about edge cases before even starting to code the solution.
