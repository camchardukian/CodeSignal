# Apple Boxes

[**Challenge Link**](https://app.codesignal.com/arcade/code-arcade/loop-tunnel/scG8AFsPuqQGx8Qjf)

**Prompt:** You have k apple boxes full of apples. Each square box of size m contains m × m apples. You just noticed two interesting properties about the boxes:

The smallest box is size 1, the next one is size 2,..., all the way up to size k.
Boxes that have an odd size contain only yellow apples. Boxes that have an even size contain only red apples.
Your task is to calculate the difference between the number of red apples and the number of yellow apples.

**Initial Thoughts:**

```
// The simple way to solve this problem would be to loop from box 1 until box 'k' incrementing and decrementing along the way.

// I don't think we actually need to do any looping though.

// The simple equation we can use to generate every answer is (k + 1) times k times 0.5.

// Then if our input k is positive we apply a unary negation operator so that we get a negative result, otherwise if k is an even number we just return the result as-is.
```

**My Solution:**

```
function solution(k) {
  const result = (k + 1) * k * 0.5;
  return k % 2 ? -result : result;
}
```

**Reflection:** My solution seems to have been almost ideal from a time complexity and conciseness standpoint.

The other most upvoted solution had the same general logic, only they were able to condense it into a single line by dividing rather than multiplying followed by a ternary operator in the next line like I did:

```
function solution(k) {
  return (k * (k + 1)) / (k % 2 ? -2 : 2);
}
```
