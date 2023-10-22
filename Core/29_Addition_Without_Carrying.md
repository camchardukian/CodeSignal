# Addition Without Carrying

[**Challenge Link**](https://app.codesignal.com/arcade/code-arcade/loop-tunnel/xzeZqCQjpfDJuN72S)

**Prompt:** A little child is studying arithmetic. They have just learned how to add two integers, written one below another, column by column. But the child always forgets about the important part - carrying.

Given two integers, your task is to find the result that the child will get.

**Initial Thoughts:**

```
// Seems like all we need to do is add the numbers in each column and then use the modulo operator to get the remainder so we only have a single digit. Alternatively, we could just take the last index to get a single digit for each column.

```

**My Solution:**

```
function solution(param1, param2) {
  const longerNumberAsString =
    param1.toString().length > param2.toString().length
      ? param1.toString()
      : param2.toString();
  let shorterNumberAsString =
    param1.toString().length <= param2.toString().length
      ? param1.toString()
      : param2.toString();
  const lengthDifference =
    longerNumberAsString.length - shorterNumberAsString.length;
  shorterNumberAsString =
    "0".repeat(lengthDifference) + shorterNumberAsString.toString();
  let childResult = "";
  for (let i = longerNumberAsString.length - 1; i >= 0; i--) {
    const addend1 = parseInt(longerNumberAsString[i]);
    const addend2 = parseInt(shorterNumberAsString[i]);
    const realSum = addend1 + addend2;
    childResult += realSum.toString()[realSum.toString().length - 1];
  }
  return Number(childResult.split("").reverse("").join(""));
}

```

**Reflection:** My solution worked, but it would've been a much better solution if I was able to make the logic more concise.

I liked how this solution used a 10x multiplier to move the different products to the tens, hundreds, thousands, etc. columns rather than have to split and reverse the result like I did:

```
function solution(param1, param2) {
  var result = 0,
    num = 1;
  while (param1 + param2 > 0) {
    num *= 10;
    result += (param1 + param2) % num;
    param1 -= param1 % num;
    param2 -= param2 % num;
  }
  return result;
}
```
