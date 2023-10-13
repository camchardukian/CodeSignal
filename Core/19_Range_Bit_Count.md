# Range Bit Count

[**Challenge Link**](https://app.codesignal.com/arcade/code-arcade/corner-of-0s-and-1s/eC2Zxu5H5SnuKxvPT)

**Prompt:** You are given two numbers a and b where 0 ≤ a ≤ b. Imagine you construct an array of all the integers from a to b inclusive. You need to count the number of 1s in the binary representations of all the numbers in the array.

**Initial Thoughts:**

```
// I think the simplest way to do this is to get an array of all the numbers between and including a and b, then use a custom callback method with the reduce function to turn each number into a binary and count the 1s.
```

**My Solution:**

```
function solution(a, b) {
    let total = 0;
    for (let i = a; i <= b; i++) {
        const numberOfOnes = i.toString(2).match(/1/g)?.length
         if (numberOfOnes) {
             total+=numberOfOnes
         }
    }
    return total;
}
```

**Reflection:** I went with a for loop approach instead of sticking to the idea in my initial thoughts that would have led to me having to create two separate arrays. Overall, I saw most of the other highly rated community submissions we're pretty similar to mine.
