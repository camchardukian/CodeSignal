# longestDigitsPrefix

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-9/AACpNbZANCkhHWNs3)

**Prompt:** Given a string, output its longest prefix which contains only digits.

**Initial Thoughts:**

```
// There's a couple ways we could solve this. There's the obvious brute force solution of looping through the inputString and evaluating whether each given character is a number or not.

// I think the better option, however, would be to use indexOf or regex .search() to check the index of the first non-digit character.

// Then, if indexOf is 0, we return an empty string, if indexOf is -1, we return the whole string, if indexOf is a positive integer, we return inputString.split().slice(0, indexOfValue).join().
```

**Solution:**

```
function solution(inputString) {
    const indexOfFirstNonDigit = inputString.search(/\D/);
    if (indexOfFirstNonDigit === 0) {
        return ""
    } else if (indexOfFirstNonDigit === -1) {
        return inputString;
    }
    return inputString.split("").slice(0, indexOfFirstNonDigit).join("")
}
```

**Reflection:** I could've had a simpler more efficient solution. All I needed to do was use regex, .match(), and return the first element of the matched array:

```
function solution(inputString) {
    return inputString.match(/^\d*/)[0]
}
```
