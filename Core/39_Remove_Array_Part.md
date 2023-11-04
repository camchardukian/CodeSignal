# Remove Array Part

[**Challenge Link**](https://app.codesignal.com/arcade/code-arcade/list-forest-edge/vPJB7T28fyCeh2Ljn)

**Prompt:** Remove a part of a given array between given 0-based indexes l and r (inclusive).

**Initial Thoughts:**

```
// I think we can just use slice here to remove the indexes we don't want between l and r.
```

**My Solution:**

```
function solution(inputArray, l, r) {
  return inputArray.slice(0, l).concat(inputArray.slice(r + 1));
}

```

**Reflection:** I see my solution was both concise and pretty performant. If we were searching for an alternate approach, however, we could've also solved this problem by filtering the unwanted indexes out via the `.filter()` method.
