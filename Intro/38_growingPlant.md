# growingPlant

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-9/xHvruDnQCx7mYom3T)

**Prompt:** Caring for a plant can be hard work, but since you tend to it regularly, you have a plant that grows consistently. Each day, its height increases by a fixed amount represented by the integer upSpeed. But due to lack of sunlight, the plant decreases in height every night, by an amount represented by downSpeed.

Since you grew the plant from a seed, it started at height 0 initially. Given an integer desiredHeight, your task is to find how many days it'll take for the plant to reach this height.

**Initial Thoughts:**

```
// I think we can loop through and check at the end of everyday if we've reached the desired height and if not decrement by downSpeed before continuing to the next day.
```

**Solution:**

```
function solution(upSpeed, downSpeed, desiredHeight) {
  let numberOfDays = 0,
    height = 0;
  while (true) {
    numberOfDays++;
    height += upSpeed;
    if (height >= desiredHeight) {
      return numberOfDays;
    }
    height -= downSpeed;
  }
}
```

**Reflection:** My solution was decent, but I could've improved the performance by skipping the loop and instead writing a solution like this:

```
function solution(upSpeed, downSpeed, desiredHeight) {
    if(upSpeed>=desiredHeight)return 1;
    return Math.ceil((desiredHeight-downSpeed)/(upSpeed-downSpeed));
}
```
