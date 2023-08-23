# isLucky

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-3/3AdBC97QNuhF6RwsQ)

**Prompt:** Ticket numbers usually consist of an even number of digits. A ticket number is considered lucky if the sum of the first half of the digits is equal to the sum of the second half.

Given a ticket number n, determine if it's lucky or not.

**Pseudocode:**

```
// We are guaranteed the input will have an even number of digits.

// This means we parse the number into a string, take the length, and divide the length by two to get the quantity of integers for each half.

// We then declare two variables firstHalfCount and secondHalfCount.

// We loop through the first "x" characters, parse them as numbers and increment firstHalfCount. We then do the same for secondHalfCount.

// Finally, we check if firstHalfCount equals secondHalfCount and if so we return true, otherwise we return false.
```

**Solution:**

```
function solution(n) {
  const numberAsString = n.toString();
  const numberOfDigits = numberAsString.length;
  const digitsPerHalf = numberOfDigits / 2;
  let firstHalfCount = 0,
    secondHalfCount = 0;

  for (let i = 0; i < numberOfDigits; i += 1) {
    if (i < digitsPerHalf) {
      firstHalfCount += Number(numberAsString[i]);
    } else {
      secondHalfCount += Number(numberAsString[i]);
    }
  }
  return firstHalfCount === secondHalfCount;
}
```

**Reflection:** I had an idea for a solution probably 30 seconds after reading through the problem. The only thing that tripped me up was I thought when declaring multiple variables on a single line that I only had to use the equal sign once, but actually it needs to be used twice if you want both variables to be initialized to some provided values.

One thing I noticed in retrospect was I didn't actually need to declare two variables. Instead, I could've had a single variable called `count` or something like that and incremented it for the first half of the digits and decremented it for the second half of the digits.

Then, I'd know that if `count` was 0 the first half and second half sums were the same. That solution may have performed ever so slightly better than mine, but I also think it might have been slightly less readable so I think everything balances out in the end.
