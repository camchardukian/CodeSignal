# Reach Next Level

[**Challenge Link**](https://app.codesignal.com/arcade/code-arcade/at-the-crossroads/m9wjpkCjgofg7gs8N)

**Prompt:** You are playing an RPG game. Currently your experience points (XP) total is equal to experience. To reach the next level your XP should be at least at threshold. If you kill the monster in front of you, you will gain more experience points in the amount of the reward.

Given values experience, threshold and reward, check if you reach the next level after killing the monster.

**Initial Thoughts:**

```
// Seems like all I need to do is check that experience plus reward is equal to or greater than threshold.
```

**My Solution:**

```
function solution(experience, threshold, reward) {
  return experience + reward >= threshold;
}
```

**Reflection:** My initial thoughts were exactly what we needed for an optimal solution to this challenge.
