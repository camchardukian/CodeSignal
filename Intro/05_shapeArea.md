# shapeArea

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-2/yuGuHvcCaFCKk56rJ)

**Prompt:** Below we will define an n-interesting polygon. Your task is to find the area of a polygon for a given n.

A 1-interesting polygon is just a square with a side of length 1. An n-interesting polygon is obtained by taking the n - 1-interesting polygon and appending 1-interesting polygons to its rim, side by side. You can see the 1-, 2-, 3- and 4-interesting polygons in the picture below.

**Solution:**

```
function solution(n) {
    return Math.pow(n, 2) + Math.pow(n - 1, 2)
}
```

**Reflection:** Again, I felt my solution was clearer and more concise than most of the alternative JS solutions I saw. I was able to find a pattern by observing how much the area was increasing each time and soon after identified that we could find the answer by squaring the current input and adding it the previously squared input.
