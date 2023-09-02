# Box Blur

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-5/5xPitc3yT3dqS7XkP)

**Prompt:** Last night you partied a little too hard. Now there's a black and white photo of you that's about to go viral! You can't let this ruin your reputation, so you want to apply the box blur algorithm to the photo to hide its content.

The pixels in the input image are represented as integers. The algorithm distorts the input image in the following way: Every pixel x in the output image has a value equal to the average value of the pixel values from the 3 × 3 square that has its center at x, including x itself. All the pixels on the border of x are then removed.

Return the blurred image as an integer, with the fractions rounded down.

**Initial Thoughts:**

```
// First, we need to see if a pixel (which is represented by integers), is surrounded by other integers.

// We can do this by looping through the entire 2d image array. We can start at index 1, of the item at index 1. Then we check if if the previous array index - 1 , previous array index, previous array index + 1, index - 1, index + 1, next array index - 1, next array index, and next array index + 1 all have values.

// If they do, we can sum up all of those values and do Math.floor(sum / 9). Then we push this value to an array of blurredPixels.

// We loop through the entire array and when we finish, we take the square root of blurredPixels.length to calculate how many internal arrays there should be and how many items each array should have.
```

**Solution:**

```
function solution(image) {
  const blurSize = 9;
  const oneDimensionBlurredPixelsArray = [];
  const twoDimensionBlurredPixelsArray = [];
  for (let i = 1; i <= image.length - 2; i++) {
    for (let ii = 1; ii <= image[i].length - 2; ii++) {
      const pixels = [
        image[i - 1][ii - 1],
        image[i - 1][ii],
        image[i - 1][ii + 1],
        image[i][ii - 1],
        image[i][ii],
        image[i][ii + 1],
        image[i + 1][ii - 1],
        image[i + 1][ii],
        image[i + 1][ii + 1],
      ];
      const invalidPixels = pixels.filter((item) => isNaN(item));
      if (!invalidPixels.length) {
        oneDimensionBlurredPixelsArray.push(
          Math.floor(pixels.reduce((a, b) => a + b) / blurSize)
        );
      }
    }
  }
  while (oneDimensionBlurredPixelsArray.length) {
    twoDimensionBlurredPixelsArray.push(
      oneDimensionBlurredPixelsArray.splice(0, image[0].length - 2)
    );
  }
  return twoDimensionBlurredPixelsArray;
}

```

**Reflection:** After solving this problem I looked at some other solutions to see if I could learn any tricks. I saw one of the top rated answers took a similar approach to me, but his solution was likely a bit more efficient because he sliced the borders via slicing and mapping:

```
var B = I.slice(1,-1).map(e=>e.slice(1,-1))
```

Other than that, his approach to solving the problem seemed pretty similar to mine.
