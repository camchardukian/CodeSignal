# Magical Well

[**Challenge Link**](https://app.codesignal.com/arcade/code-arcade/loop-tunnel/LbuWRHnMoJH9SAo4o)

**Prompt:** You are standing at a magical well. It has two positive integers written on it: a and b. Each time you cast a magic marble into the well, it gives you a \* b dollars and then both a and b increase by 1. You have n magic marbles. How much money will you make?

**Initial Thoughts:**

```
// I think we could either use a for loop or recursion for this problem. The for loop is probably better.

// The main idea is that we need to do a * b, increment by 1, and repeat 'n' times.
```

**My Solution:**

```
function solution(a, b, n) {
  let money = 0;
  for (let i = 0; i < n; i++) {
    money += a * b;
    a++, b++;
  }
  return money;
}
```

**Reflection:** My solution was good enough, but I actually liked this solution that utilized a ternary operator and recursion more:

```
function solution(a, b, n) {
  return n != 0 ? a * b + solution(++a, ++b, --n) : 0;
}
```
