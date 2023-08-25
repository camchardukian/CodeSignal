# Sort by Height

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-3/D6qmdBL2NYz49XHwM)

**Prompt:** Some people are standing in a row in a park. There are trees between them which cannot be moved. Your task is to rearrange the people by their heights in a non-descending order without moving the trees. People can be very tall!

**Pseudocode:**

```
// I think the bruteforce solution would be to first loop through the entire array and note the indexes of the trees (the -1s), and remove the trees.

// We could then use a sort function to sort the array without trees from smallest to largest.

// Finally, we'd then loop through the treeIndexes array, and use the values at each index to insert the items back into the sorted array.

```

**Solution:**

```
function solution(a) {
  const treeIndexes = [];
  const arrayWithoutTrees = [...a];
  for (let i = a.length - 1; i >= 0; i -= 1) {
    if (a[i] === -1) {
      treeIndexes.push(i);
      arrayWithoutTrees.splice(i, 1);
    }
  }

  const sortedArray = arrayWithoutTrees.sort((a, b) => a - b);

  for (let i = treeIndexes.length - 1; i >= 0; i -= 1) {
    sortedArray.splice(treeIndexes[i], 0, -1);
  }
  return sortedArray;
}
```

**Reflection:** While my original pseudocode idea had the right concept, in reality I should have remembered that it's almost always better to loop backwards when removing indexes from an array.

That cost me a few minutes when implementing the solution, and required me to submit a couple times before I correctly diagnosed that was the issue.

After I finished solving the problem, I found a pretty clever solution from another dev where they created an array of positive integers by filtering out the -1s.

They then used a map function on the original array and did a check so that whenever the original array had a positive number they would return the corresponding value from the `positiveIntegers` array, otherwise they'd simply return -1.
