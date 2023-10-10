# Metro Card

[**Challenge Link**](https://app.codesignal.com/arcade/code-arcade/at-the-crossroads/J7PQDxpWqhx7HrvBZ)

**Prompt:** You just bought a public transit card that allows you to ride the Metro for a certain number of days.

Here is how it works: upon first receiving the card, the system allocates you a 31-day pass, which equals the number of days in January. The second time you pay for the card, your pass is extended by 28 days, i.e. the number of days in February (note that leap years are not considered), and so on. The 13th time you extend the pass, you get 31 days again.

You just ran out of days on the card, and unfortunately you've forgotten how many times your pass has been extended so far. However, you do remember the number of days you were able to ride the Metro during this most recent month. Figure out the number of days by which your pass will now be extended, and return all the options as an array sorted in increasing order.

**Initial Thoughts:**

```
// The first thing we need is an array with the number of days in each month.

// Then, based on the lastNumberOfDays, we can find each month with lastNumberOfDays, and then push the following month's number of days into an array.

// If there is no next month (meaning we're at index 11), we should add January's dayCount (31).

// Finally, we generate an array from a set of possible options (to get the unique options) and use the sort method to sort all the options in increasing order.
```

**My Solution:**

```
function solution(lastNumberOfDays) {
  const daysInEachMonth = [31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31];
  const possibleNumberOfDays = [];
  for (let i = 0; i < daysInEachMonth.length; i++) {
    if (daysInEachMonth[i] === lastNumberOfDays) {
      if (i < daysInEachMonth.length - 1) {
        possibleNumberOfDays.push(daysInEachMonth[i + 1]);
      } else {
        possibleNumberOfDays.push(daysInEachMonth[0]);
      }
    }
  }
  return Array.from(new Set(possibleNumberOfDays)).sort((a, b) => a - b);
}
```

**Reflection:** I saw that there were other answers that more or less hard coded the answer:

```
function solution(lastNumberOfDays) {
    var result = {
        30: [31],
        28: [31],
        31: [28, 30, 31]
    };
    return result[lastNumberOfDays];
}
```

While that's definitely a more concise solution than the one I came up with, I thought the spirit of the problem was to come up with a solution that could be more flexible for other theoretical calendars that may have different amounts of days in each month.

With that being said, I think both approaches are completely valid, and this would've been a clarifying question I would've asked if I received this problem in an actual interview.
