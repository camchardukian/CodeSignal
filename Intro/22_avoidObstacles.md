# avoidObstacles

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-5/XC9Q2DhRRKQrfLhb5)

**Prompt:** You are given an array of integers representing coordinates of obstacles situated on a straight line.

Assume that you are jumping from the point with coordinate 0 to the right. You are allowed only to make jumps of the same length represented by some integer.

Find the minimal length of the jump enough to avoid all the obstacles.

**Initial thoughts:**

```
// As I'm looking at this problem I'm brought back to elementary or middle school math classes when we talked about greatest common factor, least common multiple, stuff like that.

// There's probably some more efficient solution, but I think I can at least brute force the solution by taking the largest number in the array + 1, and then trying to loop through the array.

// Here I'm at a crossroads, the first option is I can loop through the array and increment our currentPoint until we either get to largest number in the array + 1, or I can use the modulo operator along with minimumJumpLength on each value in the array as we loop through. I think in most cases this 2nd approach will be more efficient.
```

**Solution:**

```
function solution(inputArray) {
    let minimumJumpLength = 2;
    for (let i = 0; i < inputArray.length; i++) {
        if (minimumJumpLength <= inputArray[i]) {
        if (!(inputArray[i] % minimumJumpLength)) {
            i = -1;
            minimumJumpLength++;
        }
        }
    }
    return minimumJumpLength;
}
```

**Reflection:** Some other solutions used a _while_ loop along with the _.some()_ method. Their approach was slightly more concise than mine, and a nice alternative versus the approach to this problem I came up with.

The most important takeaway I took from this problem was that if I want to "reset" a for-loop, I need to keep in mind that my iterator will be incremented/decremented before the next iteration of the loop.

In the above solution, you can see that this means it's necessary to set `i` to `-1` instead of `0`.
