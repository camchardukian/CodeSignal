# Will You?

[**Challenge Link**](https://app.codesignal.com/arcade/code-arcade/at-the-crossroads/jZ4ZSiGohzFTeg4yb)

**Prompt:** Once Mary heard a famous song, and a line from it stuck in her head. That line was "Will you still love me when I'm no longer young and beautiful?". Mary believes that a person is loved if and only if he/she is both young and beautiful, but this is quite a depressing thought, so she wants to put her belief to the test.

Knowing whether a person is young, beautiful and loved, find out if they contradict Mary's belief.

A person contradicts Mary's belief if one of the following statements is true:

they are young and beautiful but not loved;
they are loved but not young or not beautiful.

**Initial Thoughts:**

```
// We need to return true if someone contradicts Mary's belief.

// The solution to this problem seems to be to check if young is true and beautiful is true, then we return the inverse of loved (!loved).

// Otherwise if one or both of young and beautiful are false, we return loved.
```

**My Solution:**

```
function solution(young, beautiful, loved) {
  if (young && beautiful) {
    return !loved;
  }
  return loved;
}
```

**Reflection:** My logic was on point, but I could have made the solution slightly more concise by writing it like this:

```
function solution(young, beautiful, loved) {
  return (young && beautiful) != loved;
}
```
