# Sudoku

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-12/tQgasP8b62JBeirMS)

**Prompt:** Sudoku is a number-placement puzzle. The objective is to fill a 9 × 9 grid with digits so that each column, each row, and each of the nine 3 × 3 sub-grids that compose the grid contains all of the digits from 1 to 9.

This algorithm should check if the given grid of numbers represents a correct solution to Sudoku.

**Initial Thoughts:**

```
// My first instinct is to simply loop through each row and see if all are valid sudoku solutions. Then do the same for each column. Finally, do the same for each 3 x 3 grid.

// Looping through each column and row should be straightforward. I think to loop through each 3 x 3 grid I can use nested for loops.

// It may not be the most ideal solution, but I think I can put something together that solves the problem and then look for a more optimal solution in the community submissions later.
```

**My Solution:**

```
function solution(grid) {
  // check rows
  for (let i = 0; i < grid.length; i++) {
    const sortedRow = [...grid[i]].sort((a, b) => a - b);
    for (let ii = 1; ii <= sortedRow.length; ii++) {
      if (ii !== sortedRow[ii - 1]) {
        return false;
      }
    }
  }
  // check columns
  for (let i = 0; i < grid.length; i++) {
    let column = [];
    for (let ii = 0; ii < grid.length; ii++) {
      if (column.includes(grid[ii][i])) {
        return false;
      }
      column.push(grid[ii][i]);
    }
  }
  // check grids
  for (let row = 0; row < grid.length; row += 3) {
    for (let col = 0; col < grid[row].length; col += 3) {
      let subgrid = [];
      for (let i = row; i < row + 3; i++) {
        for (let ii = col; ii < col + 3; ii++) {
          if (subgrid.includes(grid[i][ii])) {
            return false;
          }
          subgrid.push(grid[i][ii]);
        }
      }
    }
  }
  // no issues were detected with the rows, columns, or grids so we return true.
  return true;
}
```

**Reflection:** My solution was ok. One obvious (in hindsight) way I could've improved my solution would be to use `Sets` to check for duplicates when checking rows, rather than nested looping.

I guess the one redeeming factor is my nested loops would return false if there was a number outside of the 1-9 range, but overall given the constraints of the problem using the Sets would've been more efficient.
