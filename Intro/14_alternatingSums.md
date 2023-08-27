# alternatingSums

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-4/cC5QuL9fqvZjXJsW9)

**Prompt:** Several people are standing in a row and need to be divided into two teams. The first person goes into team 1, the second goes into team 2, the third goes into team 1 again, the fourth into team 2, and so on.

You are given an array of positive integers - the weights of the people. Return an array of two integers, where the first element is the total weight of team 1, and the second element is the total weight of team 2 after the division is complete.

**Pseudocode:**

```
// This problem seems pretty simple. We can initialize two variables to 0, and then loop through the array.

// We increment the first variable for each number that's 0 or an even number, and we increment the second variable for each odd number.

// After we finish looping, we return an array with the two variables.
```

**Solution:**

```
function solution(a) {
    let team1 = 0, team2 = 0;
    for (let i = 0; i < a.length; i++) {
        if (i % 2) {
            team2 += a[i]
        } else {
            team1 += a[i]
        }
    }
    return [team1, team2]
}
```

**Reflection:** After looking at some of the other solutions, I'm happy with my solution. This problem helped boost my confidence again, which had taken a little bit of a hit after the difficult problem yesterday.
