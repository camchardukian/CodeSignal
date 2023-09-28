# Seats in Theater

[**Challenge Link**](https://app.codesignal.com/arcade/code-arcade/intro-gates/bszFiQAog96G9CXKg)

**Prompt:** Your friend advised you to see a new performance in the most popular theater in the city. He knows a lot about art and his advice is usually good, but not this time: the performance turned out to be awfully dull. It's so bad you want to sneak out, which is quite simple, especially since the exit is located right behind your row to the left. All you need to do is climb over your seat and make your way to the exit.

The main problem is your shyness: you're afraid that you'll end up blocking the view (even if only for a couple of seconds) of all the people who sit behind you and in your column or the columns to your left. To gain some courage, you decide to calculate the number of such people and see if you can possibly make it to the exit without disturbing too many people.

Given the total number of rows and columns in the theater (nRows and nCols, respectively), and the row and column you're sitting in, return the number of people who sit strictly behind you and in your column or to the left, assuming all seats are occupied.

**Initial Thoughts:**

```
// Ok, they've slightly ramped up the difficulty of the problems again beyond the 30 second brain teaser difficulty level of the past few problems.

// This problem still seems pretty straightforward though. We need to multiply the number of columns sitting directly behind us or to our left times the number of rows behind us.

// This means our row should not be included in the number of people bothered because they are not behind us, but anybody sitting in our column behind us should be included.

// This means we should have something like the following to calculate our answer (we -1 from column to include our own column for people who could potentially be bothered): nCols - (col - 1) * nRows - row
```

**My Solution:**

```
function solution(nCols, nRows, col, row) {
  return (nCols - (col - 1)) * (nRows - row);
}
```

**Reflection:** Again, my solution matched the top community submission pretty much character for character (I think this problem was actually an exact match).

On to the next problem...
