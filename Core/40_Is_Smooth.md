# Is Smooth?

[**Challenge Link**](https://app.codesignal.com/arcade/code-arcade/list-forest-edge/3LmZafR9wMCWpdgra)

**Prompt:** We define the middle of the array arr as follows:

if arr contains an odd number of elements, its middle is the element whose index number is the same when counting from the beginning of the array and from its end;

if arr contains an even number of elements, its middle is the sum of the two elements whose index numbers when counting from the beginning and from the end of the array differ by one.

An array is called smooth if its first and its last elements are equal to one another and to the middle. Given an array arr, determine if it is smooth or not.

**Initial Thoughts:**

```
// We need to check if the first, last, and middle items are the same. We need to be aware of handling even and odd array lengths a bit differently.

// We also need to be sure to account for both positive and negative numbers.

// So, we just need to account for the two different cases of the middleItem (odd/even), assign the appropriate value to middleItem, and then use a Set to ensure the first, middle, and last items are all the same.
```

**My Solution:**

```
function solution(arr) {
  let middleItem;
  const halfArrLength = arr.length / 2;
  if (arr.length % 2) {
    middleItem = arr[Math.floor(halfArrLength)];
  } else {
    middleItem = arr[halfArrLength - 1] + arr[halfArrLength];
  }

  return new Set([arr[0], middleItem, arr[arr.length - 1]]).size === 1;
}
```

**Reflection:** Seems my solution was a pretty good balance of being concise, readable, and efficient.
