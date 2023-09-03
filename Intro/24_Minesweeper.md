# Minesweeper

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-5/ZMR5n7vJbexnLrgaM)

**Prompt:** In the popular Minesweeper game you have a board with some mines and those cells that don't contain a mine have a number in it that indicates the total number of mines in the neighboring cells. Starting off with some arrangement of mines we want to create a Minesweeper game setup.

**Initial thoughts:**

```
// I think this problem is similar to the previous problem I solved. We need to check all of the potential items that border a given item, and then sum up the number of trues.

// We can do this by looping through the array, and then summing the length of the filtered array, and pushing that item to a 1d array, and then formatting it to a 2d array later like in the previous problem.
```

**Solution:**

```
function solution(matrix) {
  const oneDimensionalArray = [];
  const twoDimensionalArray = [];
  for (let i = 0; i < matrix.length; i++) {
    for (let ii = 0; ii < matrix[i].length; ii++) {
      const surroundingItems = [];
      if (matrix[i - 1]) {
        surroundingItems.push(
          matrix[i - 1][ii - 1],
          matrix[i - 1][ii],
          matrix[i - 1][ii + 1]
        );
      }
      surroundingItems.push(matrix[i][ii - 1], matrix[i][ii + 1]);
      if (matrix[i + 1]) {
        surroundingItems.push(
          matrix[i + 1][ii - 1],
          matrix[i + 1][ii],
          matrix[i + 1][ii + 1]
        );
      }
      oneDimensionalArray.push(surroundingItems.filter((item) => item).length);
    }
  }
  while (oneDimensionalArray.length) {
    twoDimensionalArray.push(oneDimensionalArray.splice(0, matrix[0].length));
  }
  return twoDimensionalArray;
}
```

**Reflection:** My solution used mostly sound logic, but this solution by koviko was significantly more elegant (while still using fairly similar logic):

```
const directions = [
    [ 1,-1], [ 1, 0], [ 1, 1],
    [ 0,-1],          [ 0, 1],
    [-1,-1], [-1, 0], [-1, 1]
];

solution = matrix => matrix.map((row, y) => row.map((col, x) => directions.reduce((count, i) => count += !!(matrix[y + i[0]] && matrix[y + i[0]][x + i[1]]), 0)));
```
