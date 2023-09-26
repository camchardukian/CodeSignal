# Largest Number

[**Challenge Link**](https://app.codesignal.com/arcade/code-arcade/intro-gates/SZB5XypsMokGusDhX)

**Prompt:** Given an integer n, return the largest number that contains exactly n digits.

**Initial Thoughts:**

```// This problem seems simple. Logially, the largest number that contains exactly n digits would be 9 repeated n times. For example if n was 3 we should return 999.

// So, here are two fairly straightforward ways we could solve this problem. One, we could turn n into a string, and then use the .repeat() method with n passed in as the argument for number of repetitions.

// Otherwise, to avoid parsing the number as a string we could do 10 to the nth power and then subtract 1 from the product.

// This would work because we take the smallest possible number with n + 1 digits, and then subtract 1 from that number to get the largest number with n digits.
```

**My Solution:**

```
function solution(n) {
  return Math.pow(10, n) - 1;
}
```

**Reflection:** The two solutions I proposed in my 'initial thoughts' were the top two solutions in the community submissions so I don't think I could've been much more on point for this problem.
