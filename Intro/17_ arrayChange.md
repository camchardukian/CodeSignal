# arrayChange

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-4/xvkRbxYkdHdHNCKjg)

**Prompt:** You are given an array of integers. On each move you are allowed to increase exactly one of its element by one. Find the minimal number of moves required to obtain a strictly increasing sequence from the input.

**Pseudocode:**

```
// This problem has a lot of thumbs down so I'm wary there may be some error or some ambiguous edge case.

// The way the description is worded makes it sound as though I'm not allowed to rearrange the numbers in the array. If rearranging is not allowed, I think the only thing I have to do is loop through the array, and check that current number - prevNumber are at least 1.

// If the currentNumber - prevNumber are not at least 1, I need to calculate what value would make them at least 1. I think I could do this using Math.abs to convert potential negative numbers into corresponding positive integers (while also not interfering with a currentNumber - prevNumber of 0) and then add 1. Then I increment minimumMoves by the result of this equation.

// I would also need to ensure I return a modified array that accounts for the new updated value at the current index.

// Finally, I continue going through the previous steps until I've looped through the entire array. Then, I return minimumMoves as the solution.
```

**Solution:**

```
function solution(inputArray) {
    let minimumMoves = 0;
    const inputArrayCopy = [...inputArray];
    for (let i = 1; i < inputArrayCopy.length; i++) {
        if ((inputArrayCopy[i] - inputArrayCopy[i - 1]) < 1 ) {
            const movesToAdd = Math.abs(inputArrayCopy[i] - inputArrayCopy[i - 1]) + 1;
            inputArrayCopy[i] = inputArrayCopy[i] + movesToAdd;
            minimumMoves += movesToAdd
        }
    }
    return minimumMoves;
}
```

**Reflection:** After reviewing other solutions I think my solution did a good job of balancing conciseness and readability.
