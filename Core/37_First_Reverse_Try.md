# First Reverse Try

[**Challenge Link**](https://app.codesignal.com/arcade/code-arcade/list-forest-edge/ND8nghbndTNKPP4Tb)

**Prompt:** Reversing an array can be a tough task, especially for a novice programmer. Mary just started coding, so she would like to start with something basic at first. Instead of reversing the array entirely, she wants to swap just its first and last elements.

Given an array arr, swap its first and last elements and return the resulting array.

**Initial Thoughts:**

```
// We can clone the array, and then directly assign values to the first and last item in the array, thus "swapping" the first and last item.
```

**My Solution:**

```
function solution(arr) {
  const arrClone = [...arr];
  if (arr.length) {
    arrClone[0] = arr[arr.length - 1];
    arrClone[arrClone.length - 1] = arr[0];
  }
  return arrClone;
}
```

**Reflection:** It seems my solution was solid. The key here was to check that the original array wasn't empty so that we wouldn't accidentally assign null values to the `arrClone` before returning it.
