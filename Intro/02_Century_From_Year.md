# centuryFromYear

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-1/egbueTZRRL5Mm4TXN)

**Prompt:** Given a year, return the century it is in. The first century spans from the year 1 up to and including the year 100, the second - from the year 101 up to and including the year 200, etc.

**Solution:**

```
function solution(year) {
    for (let i = 1; i <= 21; i+=1) {
        if (i * 100 >= year) {
            return i;
        }
    }
}
```

**Reflection:** While my brute force solution I came up with in a couple minutes worked, it would've been more efficient to return `Math.ceil(year / 100)` to avoid having to waste resources on multiple loop iterations.
