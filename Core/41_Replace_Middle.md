# Replace Middle

[**Challenge Link**](https://app.codesignal.com/arcade/code-arcade/list-forest-edge/APD5T5CybxTtfkdjL)

**Prompt:** We define the middle of the array arr as follows:

if arr contains an odd number of elements, its middle is the element whose index number is the same when counting from the beginning of the array and from its end;

if arr contains an even number of elements, its middle is the sum of the two elements whose index numbers when counting from the beginning and from the end of the array differ by one.

Given array arr, your task is to find its middle, and, if it consists of two elements, replace those elements with the value of middle. Return the resulting array as the answer.

**Initial Thoughts:**

```
// We can use the modulo operator to see if the number of items in array is even or odd.

// If odd we just return arr. If even we slice the numbers before the middleNumbers, then concat the sum of the two middle numbers, then slice the numbers after the middleNumbers.
```

**My Solution:**

```
function solution(arr) {
  if (arr.length % 2) {
    return arr;
  }
  const halfArrayLength = arr.length / 2;
  return arr
    .slice(0, halfArrayLength - 1)
    .concat(arr[halfArrayLength - 1] + arr[halfArrayLength])
    .concat(arr.slice(halfArrayLength + 1));
}
```

**Reflection:** My solution was ok, but as you can see it got a bit wordy. It seems like using the `.splice()` method may have made for a cleaner solution:

```
function solution(arr) {
  if (arr.length % 2 === 0) {
    let middleIndex = arr.length / 2 - 1;
    let sum = arr[middleIndex] + arr[middleIndex + 1];
    arr.splice(middleIndex, 2, sum);
  }
  return arr;
}
```
