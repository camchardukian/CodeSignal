# Different Squares

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-12/fQpfgxiY6aGiGHLtv)

**Prompt:** Given a rectangular matrix containing only digits, calculate the number of different 2 × 2 squares in it.

**Initial Thoughts:**

```
// Ok, it took me a while to understand that they are searching for unique 2x2 grid values, and not just how many differently located 2x2 grids there are in the matrix given to us.

// I do feel this problem is pretty similar to one of the problems I solved a week or two ago about blurring the image (Update: It was problem #23 box blur I was thinking of).

// First check that there are at least two items in the array, and each array item itself has at least two items, otherwise return 0.

// Then we start looping from index one in item 1 and go all the way until the end of item 1. Then we continue through the 2nd to last row.

// After we add all of the items into an array, we then apply some method to find all of the unique combinations.
```

**My Solution:**

```
function solution(matrix) {
  let arrayOfSquares = [];
  for (let i = 0; i < matrix.length - 1; i++) {
    for (let ii = 1; ii < matrix[i].length; ii++) {
      arrayOfSquares.push(
        `${matrix[i][ii]}${matrix[i][ii - 1]}${matrix[i + 1][ii]}${
          matrix[i + 1][ii - 1]
        }`
      );
    }
  }
  return [...new Set(arrayOfSquares)].length;
}
```

**Reflection:** I think I gained some good knowledge from this problem.

For one, I think this problem will help internalize the usage of `Sets` in finding unique values in a collection of items.

Another thing I learned is that the `.toString()` method also works for converting arrays to strings, whereas previously I thought it was only for converting numbers to strings.
