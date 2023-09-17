# deleteDigit

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-11/vpfeqDwGZSzYNm2uX)

**Prompt:** Problem: Given some integer, find the maximal number you can obtain by deleting exactly one digit of the given number. Example: For n = 152, the output should be solution(n) = 52; For n = 1001, the output should be solution(n) = 101.

**Initial Thoughts:**

```
// To solve this problem I think we turn the number into a string and then an array, and then we just have to sort the number from smallest to largest.

// From there, we just remove the smallest number from the array, join the array, and use parseInt to return the resulting string into a number. Actually, that won't work because the numbers would be out of order... let me think of another solution.

// What if we sort the digits to find the smallest digit, then do indexOf on the original input, and we can use splice to remove that index? Then we can join back and parseInt into a number.
```

**My Solution:**

```
function solution(n) {
  let largestNumber = 0;
  for (let i = 0; i < n.toString().length; i++) {
    let currentNumberArray = n.toString().split("");
    currentNumberArray.splice(i, 1);
    if (parseInt(currentNumberArray.join("")) > largestNumber) {
      largestNumber = parseInt(currentNumberArray.join(""));
    }
  }
  return largestNumber;
}

```

**Reflection:** You can see from my initial thoughts that I overcomplicated this problem a bit and went down the wrong path because I didn't think about a wide enough variety of edge cases that could occur.

Eventually I was able to come up with the solution above.

Afterwards, I saw there was a similar, though more concise and refined solution posted in the comments:

```
function solution(n) {
  s = n.toString();
  return Math.max(
    ...[...Array(s.length).keys()].map((i) =>
      Number(s.slice(0, i) + s.slice(i + 1))
    )
  );
}
```
