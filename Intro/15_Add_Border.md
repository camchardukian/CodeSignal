# Add Border

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-4/ZCD7NQnED724bJtjN)

**Prompt:** Given a rectangular matrix of characters, add a border of asterisks(\*) to it.

**Pseudocode:**

```
// From my understanding, the number of asterisks in the first and final row will be picture[0] + 2. I can assume this because the input/ouput stated that the array will consist of non-empty equal length strings.

// So, to solve this problem we can create a new outputArray which will be initialized to contain one string containing the number of asterisks calculated in the step above.

// We can then loop through picture and push each string wrapped with asterisks to outputArray.

// When we finish looping, we push one more item to outputArray that contains the number of asterisks calculated in step 1.

// Finally, we return the result.
```

**Solution:**

```
function solution(picture) {
    const asterisks = "*".repeat(picture[0].length + 2);

    const outputArray = [asterisks];

    for (let i = 0; i < picture.length; i++) {
        outputArray.push(`*${picture[i]}*`);
    }
    outputArray.push(asterisks);
    return outputArray;
}
```

**Reflection:** I think my solution was almost ideal. To make it slightly more concise and performant, however, it seems I could've mapped the results of picture rather than pushing them.

An ideal solution could've looked like this:

```
function solution(picture) {
    let r = '*'.repeat(picture[0].length + 2);
    return [
        r,
        ...picture.map(x => `*${x}*`),
        r
    ];
}
```

Overall, however, I'm proud to have produced an almost ideal solution and to have learned about how I could have made my code even better.
