# chessKnight

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-11/pwRLrkrNpnsbgMndb)

**Prompt:** Given a position of a knight on the standard chessboard, find the number of different moves the knight can perform.

The knight can move to a square that is two squares horizontally and one square vertically, or two squares vertically and one square horizontally away from it. The complete move therefore looks like the letter L. Check out the image below to see all valid moves for a knight piece that is placed on one of the central squares.

**Initial Thoughts:**

```
// I'm thinking maybe the way to go here is to make a dictionary where the letters correspond to numbers (we could also use charCodes, but I think using the dictionary decreases the perceived complexity).

// Then, we loop through the 8 possible movements the knight could make (2 up 1 left, left 2 up 1, etc.), and after each movement from the start position we see if after making the movement the knight piece is still in a valid position or "out-of-bounds".
```

**My Solution:**

```
function solution(cell) {
  const dictionary = {
    a: 1,
    b: 2,
    c: 3,
    d: 4,
    e: 5,
    f: 6,
    g: 7,
    h: 8,
  };
  const knightInitialPosition = [dictionary[cell[0]], parseInt(cell[1])];
  let possibleMoves = 0;
  const isValidPosition = (position) => {
    if (
      0 < position[0] &&
      position[0] < 9 &&
      0 < position[1] &&
      position[1] < 9
    ) {
      possibleMoves++;
    }
  };

  isValidPosition([knightInitialPosition[0] + 2, knightInitialPosition[1] + 1]);
  isValidPosition([knightInitialPosition[0] + 1, knightInitialPosition[1] + 2]);
  isValidPosition([knightInitialPosition[0] - 2, knightInitialPosition[1] - 1]);
  isValidPosition([knightInitialPosition[0] - 1, knightInitialPosition[1] - 2]);
  isValidPosition([knightInitialPosition[0] + 2, knightInitialPosition[1] - 1]);
  isValidPosition([knightInitialPosition[0] + 1, knightInitialPosition[1] - 2]);
  isValidPosition([knightInitialPosition[0] - 2, knightInitialPosition[1] + 1]);
  isValidPosition([knightInitialPosition[0] - 1, knightInitialPosition[1] + 2]);
  return possibleMoves;
}
```

**Reflection:** Although my solution isn't the most concise way of solving this problem, I do think it's pretty readable and straightforward to understand.
