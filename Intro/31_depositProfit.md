# depositProfit

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-7/8PxjMSncp9ApA4DAb)

**Prompt:** You have deposited a specific amount of money into your bank account. Each year your balance increases at the same growth rate. With the assumption that you don't make any additional deposits, find out how long it would take for your balance to pass a specific threshold.

**Initial Thoughts:**

```
// Looking at this problem, it looks like a prime candidate for recursion. We can initialize a currentValue to the deposit, and numberOfYears to 0.

// If currentValue is greater than deposit, we return numberOfYears.

// If not, the function should multiply currentValue times (1 + rate). Then we recurse.
```

**Solution:**

```
function solution(deposit, rate, threshold) {
  let currentValue = deposit;
  let numberOfYears = 0;
  while (currentValue < threshold) {
    currentValue = currentValue * (1 + rate / 100);
    numberOfYears++;
  }
  return numberOfYears;
}
```

**Reflection:** It seems my solution was adequate, but that I could have made it more concise if I had thought to use the `Math.log()` function like this:

```
function solution(d, r, t) {
  return Math.ceil(Math.log(t / d) / Math.log(r / 100 + 1));
}
```
