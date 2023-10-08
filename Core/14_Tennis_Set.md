# Tennis Set

[**Challenge Link**](https://app.codesignal.com/arcade/code-arcade/at-the-crossroads/7jaup9HprdJno2diw)

**Prompt:** In tennis, the winner of a set is based on how many games each player wins. The first player to win 6 games is declared the winner unless their opponent had already won 5 games, in which case the set continues until one of the players has won 7 games.

Given two integers score1 and score2, your task is to determine if it is possible for a tennis set to be finished with a final score of score1 : score2.

**Initial Thoughts:**

```
// First we need to get a largerScore and smallerScore.

// If largerScore is less than 6, we return false.

// If largerScore is equal to 6, we make sure smallerScore is 4 or less.

// If largerScore is more than 6, we make sure largerScore - 2 is equal to smallerScore.

// Update: Maybe I misunderstood and thought this problem was a 'win by 2' scenario. Judging that this problem received 80% thumbs down votes, I wasn't the only one that got confused by the wording.

// I thought if player 2 had 6, then player 1 would need 8 to win, but player 1 actually only needs 7. You'll see this realization reflected in my final solution.
```

**My Solution:**

```
function solution(score1, score2) {
  const largerScore = score1 > score2 ? score1 : score2;
  const smallerScore = score1 < score2 ? score1 : score2;

  if (
    (largerScore === 6 && smallerScore <= 4) ||
    (largerScore === 7 && [5, 6].includes(smallerScore))
  ) {
    return true;
  }
  return false;
}
```

**Reflection:** My solution was a pretty good one. I could've simplified it a bit by calculating the larger and smaller scores using `Math.max(score1, score2)` and `Math.min(score1, score2)` rather than using ternary operators, but other than that my solution was solid.
