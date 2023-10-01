# Late Ride

[**Challenge Link**](https://app.codesignal.com/arcade/code-arcade/intro-gates/aiKck9MwwAKyF8D4L)

**Prompt:** One night you go for a ride on your motorcycle. At 00:00 you start your engine, and the built-in timer automatically begins counting the length of your ride, in minutes. Off you go to explore the neighborhood.

When you finally decide to head back, you realize there's a chance the bridges on your route home are up, leaving you stranded! Unfortunately, you don't have your watch on you and don't know what time it is. All you know thanks to the bike's timer is that n minutes have passed since 00:00.

Using the bike's timer, calculate the current time. Return an answer as the sum of digits that the digital timer in the format hh:mm would show.

**Initial Thoughts:**

```
// First we need to calculate how many hours have elapsed. We can do this by doing division with Math.floor.

// We then take the result of the Math.floor division, times it by 60,  and subtract it from n, and use that as the number of minutes.

// We can then create a string with the two numbers, split the string, and reduce it to get the sum.
```

**My Solution:**

```
function solution(n) {
  const hours = Math.floor(n / 60);
  const minutes = n - hours * 60;
  return `${hours}${minutes}`.split("").reduce((a, b) => +a + +b);
}
```

**Reflection:** I think my solution was passable and it was cool to have a natural use case for the unary plus operator for the first time.
