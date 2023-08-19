# Make Array Consecutive 2

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-2/bq2XnSr5kbHqpHGJC)

**Prompt:** Ratiorg got statues of different sizes as a present from CodeMaster for his birthday, each statue having an non-negative integer size. Since he likes to make things perfect, he wants to arrange them from smallest to largest so that each statue will be bigger than the previous one exactly by 1. He may need some additional statues to be able to accomplish that. Help him figure out the minimum number of additional statues needed.

**Solution:**

```
function solution(statues) {
    const sortedStatues = statues.sort((a, b) => a - b);
    let statuesNeeded = 0;
    for (let i = 0; i < sortedStatues.length; i+=1) {
        let currentStatue = sortedStatues[i];
        while (currentStatue + 1 < sortedStatues[i + 1]) {
            statuesNeeded+=1;
            currentStatue+=1;
        }
    }
    return statuesNeeded;
}
```

**Reflection:** I think the key for this problem was remembering that by default the JavaScript _.sort()_ method sorts by alphanumeric characters. For that reason, we need to pass a custom callback function to _.sort()_ to instead sort the integers by how large they are.
