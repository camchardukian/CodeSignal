# Array Packing

[**Challenge Link**](https://app.codesignal.com/arcade/code-arcade/corner-of-0s-and-1s/KeMqde6oqfF5wBXxf)

**Prompt:** You are given an array of up to four non-negative integers, each less than 256.

Your task is to pack these integers into one number M in the following way:

The first element of the array occupies the first 8 bits of M;
The second element occupies next 8 bits, and so on.
Return the obtained integer M.

Note: the phrase "first bits of M" refers to the least significant bits of M - the right-most bits of an integer. For further clarification see the following example.

**Initial Thoughts:**

```
// So, for this problem it looks like we need to convert the integer array into binary, reverse the order of the array, join the elements of the array, and then parseInt the joined binary strings into a single integer.
```

**My Solution:**

```
function solution(a) {
  return parseInt(
    a
      .map((number) => number.toString(2).padStart(8, "0"))
      .reverse()
      .join(""),
    2
  );
}
```

**Reflection:** My solution worked, but it seems like a more efficient solution would've looked something like this:

```
function solution(a) {
  return a.reduce((value, byte, i) => value + byte * Math.pow(256, i));
}
```
