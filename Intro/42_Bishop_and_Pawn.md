# Bishop and Pawn

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-9/6M57rMTFB9MeDeSWo)

**Prompt:** Given the positions of a white bishop and a black pawn on the standard chess board, determine whether the bishop can capture the pawn in one move.

The bishop has no restrictions in distance for each move, but is limited to diagonal movement. Check out the example below to see how it can move:

**Initial Thoughts:**

```
// Our goal is to figure out whether the bishop can capture the pawn. I think we can do that by checking if the vertical distance between the bishop and the pawn is equal to the horizontal distance between the two pieces.

// I think we can do that by calculating the absolute value difference of subtracting one piece's x-axis position (its letter) from another, as well as the absolute value difference of subtracting one piece's y-axis position (its number) from another.

// If those two values are equal, we return true. Otherwise, we return false.

// If we weren't sure whether the letter would be upper or lowercase we could make a dictionary, but because it seems the input will only include lowercase letters we can simply use charcodes.
```

**Solution:**

```
function solution(bishop, pawn) {
  const horizontalDistance = Math.abs(
    parseInt(bishop.charCodeAt(0)) - parseInt(pawn.charCodeAt(0))
  );
  const verticalDistance = Math.abs(
    parseInt(bishop.charAt(1)) - parseInt(pawn.charAt(1))
  );
  return horizontalDistance === verticalDistance;
}
```

**Reflection:** After reviewing the other solutions posted by the CodeSignal community, it seems I came up with the ideal solution from the start.

Some of their solutions were slightly more concise because they didn't declare variables, but I still like my solution because I think it more clearly illustrates how the solution works.
