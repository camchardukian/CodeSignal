# Valid Time

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-12/ywMyCTspqGXPWRZx5)

**Prompt:** Check if the given string is a correct time representation of the 24-hour clock.

**Initial Thoughts:**

```
// If 24:00 return true. Else
// first character is 0-2, if 0-1 second character is 0-9 else 0-4, third character is colon, fourth character is 0-5, fifth character is 0-9.

// We can fairly easily do a for loop to solve this problem, or maybe solve it using regex with lookaheads/lookbehinds.

// I think the regex will be pretty complicated to solve without referencing any other resources so I'll just solve it with a for loop and then research more about regex after.
```

**My Solution:**

```
function solution(time) {
  if (
    parseInt(time[0] + time[1]) > 23 ||
    time[2] !== ":" ||
    parseInt(time[3] + time[4]) > 59 ||
    time.length > 5
  ) {
    return false;
  }
  return true;
}
```

**Reflection:** I figured we could probably have a one line solution for this problem using regex, but I didn't know how to do it off the dome.

I instead just wrote out some conditions which seemed to work ok, but I liked the community solutions better than the solution I came up with.

regex solution:

```
solution = (t) => /^([0-1]\d|2[0-3]):[0-5]\d$/.test(t);
```

concatenation Date solution:

```
function solution(time) {
  return new Date("1900-01-01 " + time) != "Invalid Date" && time != "24:00";
}
```

split solution:

```
function solution(t) {
  return t.split(":")[0] < 24 && t.split(":")[1] < 60;
}
```

While solving this problem I also learned that 24:00 wasn't a valid time, and it should have been 0:00 hahaha. Must be that post-dinner drowsiness.
