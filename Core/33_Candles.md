# Candles

[**Challenge Link**](https://app.codesignal.com/arcade/code-arcade/loop-tunnel/LAKReA3CR9EwkZGSz)

**Prompt:** When a candle finishes burning it leaves a leftover. makeNew leftovers can be combined to make a new candle, which, when burning down, will in turn leave another leftover.

You have candlesNumber candles in your possession. What's the total number of candles you can burn, assuming that you create new candles as soon as you have enough leftovers?

**Initial Thoughts:**

```

// The easy solution to this problem is to loop repeatedly, removing candles 1 at a time, and every "makeNew" number of candles we add another candle to "remainingCandles" until we reach 0.

// To be honest, that solution while probably not optimized should be good enough considering we're guaranteed to not have more than 15 candles.
```

**My Solution:**

```
function solution(candlesNumber, makeNew) {
  let burntCandles = 0;
  let candleRemains = 0;
  while (candlesNumber > 0) {
    candlesNumber--;
    candleRemains++;
    burntCandles++;
    if (candleRemains === makeNew) {
      candleRemains = 1;
      burntCandles++;
    }
  }
  return burntCandles;
}
```

**Reflection:** As I expected, there's a way to solve this problem without looping:

```
function solution(solution, makeNew) {
  return solution + Math.floor((solution - 1) / (makeNew - 1));
}
```

I'm pretty sure I could've gotten this solution myself if I was willing to spend more time optimizing my solution.

With that being said, given that I identified that further optimization would be possible ahead of time and that I want to prioritize my time and energy on problems I don't yet know how to solve, I'm satisfied with my solution.
