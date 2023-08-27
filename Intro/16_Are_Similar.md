# Are Similar?

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-4/xYXfzQmnhBvEKJwXP)

**Prompt:** Two arrays are called similar if one can be obtained from another by swapping at most one pair of elements in one of the arrays.

Given two arrays a and b, check whether they are similar.

**Pseudocode:**

```
// We need to loop through the array and count the number of times the two arrays have different values at a given index. We also need to declare a variable called indexesWithDifferentValues.

// If at any point indexesWithDifferentValues.length is greater than 2, we can immediately return false because a single swap can only "fix" two differing values.

// If we finish looping and indexesWithDifferentValues.length is 0 return true because the arrays are already the same. If 1, return false because a single swap will change 2 values. If 2, check to see if a[indexesWithDifferentValues[0]] === b[indexesWithDifferentValues[1]] and a[indexesWithDifferentValues[1]] === b[indexesWithDifferentValues[0]] to confirm the swap works. We can return the boolean that check returns as our final answer.
```

**Solution:**

```
function solution(a, b) {
    const indexesWithDifferentValues = [];
    for (let i = 0; i < a.length; i++) {
        if (a[i] !== b[i]) {
            indexesWithDifferentValues.push(i);
            if (indexesWithDifferentValues.length > 2) {
                return false;
            }
        }
    }
    if (indexesWithDifferentValues.length === 0) {
        return true;
    } else if (indexesWithDifferentValues.length === 1) {
        return false;
    }
    return a[indexesWithDifferentValues[0]] === b[indexesWithDifferentValues[1]] && a[indexesWithDifferentValues[1]] === b[indexesWithDifferentValues[0]]
}
```

**Reflection:** I looked at some other solutions and the other devs solved this using multiple filter method calls with associated callbacks, and reversing arrays.

Their logic was pretty much the same as mine thought so I don't see either my solution nor theirs as being a clear standout for "being better". On to the next challenge...
