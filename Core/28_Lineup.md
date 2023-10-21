# Lineup

[**Challenge Link**](https://app.codesignal.com/arcade/code-arcade/loop-tunnel/8rqs3BLpdKePhouQM)

**Prompt:** To prepare his students for an upcoming game, the sports coach decides to try some new training drills. To begin with, he lines them up and starts with the following warm-up exercise: when the coach says 'L', he instructs the students to turn to the left. Alternatively, when he says 'R', they should turn to the right. Finally, when the coach says 'A', the students should turn around.

Unfortunately some students (not all of them, but at least one) can't tell left from right, meaning they always turn right when they hear 'L' and left when they hear 'R'. The coach wants to know how many times the students end up facing the same direction.

Given the list of commands the coach has given, count the number of such commands after which the students will be facing the same direction.

**Initial Thoughts:**

```
// The players will be facing the same direction after each command in which the total number of Ls and Rs called thus far is an even number.
```

**My Solution:**

```
function solution(commands) {
  let leftRightCount = 0;
  let timesFacingSameDirection = 0;
  for (let i = 0; i < commands.length; i++) {
    if (["L", "R"].includes(commands[i])) {
      leftRightCount++;
    }
    if (!(leftRightCount % 2)) {
      timesFacingSameDirection++;
    }
  }
  return timesFacingSameDirection;
}
```

**Reflection:** My solution was solid, but in retrospect, I could have made it a little clearer by writing it like this:

```
function solution(commands) {
  let isFacingSameDirection = true;
  let timesFacingSameDirection = 0;
  for (let i = 0; i < commands.length; i++) {
    if (["L", "R"].includes(commands[i])) {
      isFacingSameDirection = !isFacingSameDirection;
    }
    if (isFacingSameDirection) {
      timesFacingSameDirection++;
    }
  }
  return timesFacingSameDirection;
}
```
