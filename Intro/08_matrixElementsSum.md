# matrixElementsSum

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-2/xskq4ZxLyqQMCLshr)

**Prompt:** After becoming famous, the CodeBots decided to move into a new building together. Each of the rooms has a different cost, and some of them are free, but there's a rumour that all the free rooms are haunted! Since the CodeBots are quite superstitious, they refuse to stay in any of the free rooms, or any of the rooms below any of the free rooms.

Given matrix, a rectangular matrix of integers, where each value represents the cost of the room, your task is to return the total sum of all rooms that are suitable for the CodeBots (ie: add up all the values that don't appear below a 0).

**Pseudocode:**

```
// initialize totalPrice to 0;
// initialize hauntedColumns to [].

// start at the first array and loop through it. If a given index has a 0, add it to the hauntedColumns array.

// Only add an item to the totalPrice if it's not in a hauntedColumn.

// After all iterations of the loop return totalPrice.
```

**Solution:**

```
function solution(matrix) {
    let totalPrice = 0;
    const hauntedColumns = []
    for (let i = 0; i < matrix.length; i+=1) {
        for (let ii = 0; ii < matrix[i].length; ii+=1) {
            if (hauntedColumns.includes(ii)) {
                continue;
            }
            if (matrix[i][ii] > 0) {
                totalPrice += matrix[i][ii]
                continue;
            }
            hauntedColumns.push(ii);
        }
    }
    return totalPrice;
}
```

**Reflection:** I thought this problem was pretty straightforward. To try to improve this repo, I'm going to trial adding a pseudocode section so you can better see how I'm coming to these different solutions.
