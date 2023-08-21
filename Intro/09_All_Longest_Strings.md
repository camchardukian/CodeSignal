# All Longest Strings

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-3/fzsCQGYbxaEcTr2bL)

**Prompt:** Given an array of strings, return another array containing all of its longest strings.

**Pseudocode:**

```
// sort array items by length.

// reverse loop through the array.

// if an item has a length less than the preceding item, then we break the loop because we know we've already returned all of the longest items.

// return the reversed array to ensure all items are in the original order.
```

**Solution:**

```
function solution(inputArray) {
    inputArray.sort((a, b) => a.length - b.length);
    const outputArray = [];
    outputArray.push(inputArray[inputArray.length - 1])
    for (let i = inputArray.length - 2; i >= 0; i -= 1) {
        if ((inputArray[i]).length < (inputArray[i + 1]).length) {
            break;
        }
        outputArray.push(inputArray[i])
    }
    return outputArray.reverse()
}
```

**Reflection:** To me this problem was mostly straightforward. The one catch was being able to read carefully to remember to return the items in the same order as the original `inputArray`.
