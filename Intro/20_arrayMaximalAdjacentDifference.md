# arrayMaximalAdjacentDifference

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-5/EEJxjQ7oo7C5wAGjE)

**Prompt:** Given an array of integers, find the maximal absolute difference between any two of its adjacent elements.

**Initial Thoughts:**

```
// Reading this question, it looks like some of the key things to note are absolute maximal absolute difference, adjacent elements, and the fact that the inputArray items could potentially be negative numbers.

// We also are given guaranteed constraints that the inputArray will be no longer than 10 items, so performance concerns shouldn't be too bad if we do have to loop through the full array.

// I think the simple solution would be to loop through the array starting at the 1 index, and check the Math.abs(prevItem) - Math.abs(currentItem). We can then compare the difference and see if we need to update the largestDifferenceCalculated variable.
```

**Solution:**

```
function solution(inputArray) {
    let largestDifferenceCalculated = 0;
    for (let i = 1; i < inputArray.length; i++) {
        const currentDifference = Math.abs(inputArray[i - 1] - inputArray[i]);
        if (currentDifference > largestDifferenceCalculated) {
            largestDifferenceCalculated = currentDifference;
        }
    }
    return largestDifferenceCalculated;
}
```

**Reflection:** My initial thoughts were almost correct. I just had to do a minor syntax fax with how I was calculating the Math.abs so that I better account for calculating the absolute difference between a positive and negative number.

It seems there were some more concise solutions using the spread operator, along with `.map()` and `.slice()`, but I think my solution was one of the most readable.
