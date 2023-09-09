# Knapsack Light

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-9/r9azLYp2BDZPyzaG2)

**Prompt:** You found two items in a treasure chest! The first item weighs weight1 and is worth value1, and the second item weighs weight2 and is worth value2. What is the total maximum value of the items you can take with you, assuming that your max weight capacity is maxW and you can't come back for the items later?

Note that there are only two items and you can't bring more than one item of each type, i.e. you can't take two first items or two second items.

**Initial Thoughts:**

```
// I think we need to check which value is greater, and then see if its weight is less than maxW. Then we increment currentWeight and currentValue. Then we check if currentWeight + weight of 2nd object is less than maxW.

// If so, we increment currentValue by the 2nd object.
```

**Solution:**

```
function solution(value1, weight1, value2, weight2, maxW) {
  if (weight1 <= maxW || weight2 <= maxW) {
    if (value1 >= value2) {
      if (weight1 <= maxW) {
        if (weight1 + weight2 <= maxW) {
          return value1 + value2;
        } else {
          return value1;
        }
      }
    } else {
      if (weight2 <= maxW) {
        if (weight2 + weight1 <= maxW) {
          return value2 + value1;
        } else {
          return value2;
        }
      }
      return value1;
    }
  }
  return 0;
}
```

**Reflection:** I don't like my solution much as there too much if/else nesting going on, but the alternative solutions I saw were equally confusing or outdated.
