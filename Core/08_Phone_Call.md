# Phone Call

[**Challenge Link**](https://app.codesignal.com/arcade/code-arcade/intro-gates/mZAucMXhNMmT7JWta)

**Prompt:** Some phone usage rate may be described as follows:

first minute of a call costs min1 cents,
each minute from the 2nd up to 10th (inclusive) costs min2_10 cents each minute after 10th costs min11 cents.

You have s cents on your account before the call. What is the duration of the longest call (in minutes rounded down to the nearest integer) you can have?

**Initial Thoughts:**

```
// A simple naive approach to this problem would be to decrement 's' each iteration and have a minutes variable we increment each time through the loop.

// For the first iteration we decrement by min1, the 2nd - 10th iterations we decrement by min2_10, and the following iterations we decrement by min11.
```

**My Solution:**

```
function solution(min1, min2_10, min11, s) {
  let minutes = 0;
  for (let i = 0; s > 0; i++) {
    if (minutes < 1) {
      if (s - min1 >= 0) {
        s -= min1;
        minutes += 1;
        continue;
      }
      break;
    } else if (minutes < 10) {
      if (s - min2_10 >= 0) {
        s -= min2_10;
        minutes += 1;
        continue;
      }
      break;
    } else {
      if (s - min11 >= 0) {
        s -= min11;
        minutes += 1;
        continue;
      }
      break;
    }
  }
  return minutes;
}
```

**Reflection:** My solution seemed passable and other community submissions didn't seem to be notably better.
