# chessBoardCellColor

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-6/t97bpjfrMDZH8GJhi)

**Prompt:** Given two cells on the standard chess board, determine whether they have the same color or not.

**Initial Thoughts:**

```
// I noticed that if we converted the letters into integers, (e.g "a" becomes 1, "b" becomes 2), then all of the colored cells are located at either even/even spots (2b), or odd/odd spots (3a). If a spot is even/odd, we know it's a non-colored spot.

// Thus, to determine if two spots are identical all we need to do is see is use the above rule to evaluate whether one, both, or neither of the two provided cells are colored or not.
```

**Solution:**

```
function solution(cell1, cell2) {
  const isColoredSpot = (cell) => {
    if (
      (cell.match(/[13579]/) && cell.match(/[ACEG]/)) ||
      (!cell.match(/[13579]/) && !cell.match(/[ACEG]/))
    ) {
      return true;
    }
    return false;
  };
  return isColoredSpot(cell1) === isColoredSpot(cell2);
}
```

**Reflection:** I think I came up with an effective solution for this problem, that balanced readability with conciseness.
