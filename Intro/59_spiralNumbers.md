# spiralNumbers

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-12/uRWu6K8E7uLi3Qtvx)

**Prompt:** Construct a square matrix with a size N × N containing integers from 1 to N \* N in a spiral order, starting from top-left and in clockwise direction.

**Initial Thoughts:**

```
// This problem kind of reminds me of the old phone game 'snake'.

// Our goal is to make a matrix that's n by n items long.

// There's no obvious pattern to me that sticks out for how we can populate the inner arrays.

// For that reason, I think our best bet may be to just follow the path of the snake and increment each item by one.

// First we do the entire first row of n items, then down, left, n - 1 items and up n - 2 items.

// Then we repeat the square pattern again. But this time it will start at index 1, and go right n - 2 items, down n -3 items.
```

**My Solution:**

```
function solution(n) {
  const matrix = Array.from({ length: n }, () => []);
  let currentValue = 1;
  let top = 0;
  let right = n - 1;
  let bottom = n - 1;
  let left = 0;

  while (currentValue <= n * n) {
    for (let i = left; i <= right; i++) {
      matrix[top][i] = currentValue;
      currentValue++;
    }
    top++;

    for (let i = top; i <= bottom; i++) {
      matrix[i][right] = currentValue;
      currentValue++;
    }
    right--;

    for (i = right; i >= left; i--) {
      matrix[bottom][i] = currentValue;
      currentValue++;
    }
    bottom--;
    for (let i = bottom; i >= top; i--) {
      matrix[i][left] = currentValue;
      currentValue++;
    }
    left++;
  }
  return matrix;
}
```

**Reflection:** I think this problem was way harder than it may have looked.

My initial thoughts were pretty close to how I actually implemented this feature, but the actual implementation took quite a long time trying to figue out how I should increment and decrement everything.

The community solutions were also super complicated so I would say my answer came out pretty well.

One cool thing I learned while implementing the solution is that using `Array.from()` we can pass an object with a length, and then pass a callback function function to populate our array items.

In this case, I just made the array items empty arrays.
