# Elections Winners

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-10/8RiRRM3yvbuAd3MNg)

**Prompt:** Elections are in progress!

Given an array of the numbers of votes given to each of the candidates so far, and an integer k equal to the number of voters who haven't cast their vote yet, find the number of candidates who still have a chance to win the election.

The winner of the election must secure strictly more votes than any other candidate. If two or more candidates receive the same (maximum) number of votes, assume there is no winner at all.

**Initial Thoughts:**

```
//  I think all we need to do is sort the array from largest to smallest, and then loop through all of the smaller numbers and see is smallNumber + k is greater than the largest number than increment possibleWinners by 1.

// The catch is if k is 0, then we need to make sure there's only 1 largest number and not multiple integers of the same value.
```

**Solution:**

```
function solution(votes, k) {
  const sortedArray = [...votes].sort((a, b) => b - a);
  if (k === 0) {
    const largestIntegerArray = sortedArray.filter(
      (item) => item === sortedArray[0]
    );
    return largestIntegerArray.length === 1 ? 1 : 0;
  }
  return sortedArray.filter((item) => item + k > sortedArray[0]).length;
}
```

**Reflection:** I think my solution was pretty good. We could have decreased the complexity a bit by using `Math.max(...votes)`, but overall I still think we did well. Let's keep going.
