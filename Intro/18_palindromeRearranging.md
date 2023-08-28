# palindromeRearranging

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-4/Xfeo7r9SBSpo3Wico)

**Prompt:** Given a string, find out if its characters can be rearranged to form a palindrome.

**Pseudocode:**

```
// I think we can first sort the string by alphanumeric characters. Then we take the string's length.

// If the string length is even, then the count of each individual letter must be an even number. If the string length is odd, we need to have exactly one odd number count and the rest of the letter counts need to be either even numbers or 0.

// Because the array is sorted, we can loop through the entire array starting at the 1 index and increment currentCharacterCount every time the prevCharacter is the same as the currentCharacter.

// If prevCharacter is not the same as currentCharacter, we push currentCharacter to our letterCountsArray and reset currentCharacter to 1.

// After we finish looping, we return our solution based on step #2, if the length of the inputString is even, we need to check how many odd numbers are in the letterCountsArray. If the answer is 1 or 0, then we have a palindrome.
```

**Solution:**

```
function solution(inputString) {
    const sortedString = inputString.split("").sort().join("");
    const stringLength = sortedString.length;
    const letterCountsArray = [];
    let currentCharacterCount = 1;
    for (let i = 1; i < stringLength; i++) {
        if (sortedString[i - 1] !== sortedString[i]) {
            letterCountsArray.push(currentCharacterCount);
            currentCharacterCount = 1;
            continue;
        }
        currentCharacterCount +=1;
    }
        letterCountsArray.push(currentCharacterCount);
    const lettersWithOddAmounts = letterCountsArray.filter((value) => value % 2);
    if (stringLength % 2) {
        return lettersWithOddAmounts.length === 1 ? true : false;
    }
    return lettersWithOddAmounts.length > 0 ? false : true;
}
```

**Reflection:** I saw some other clever solutions that used regex or managed to convert all of my logic into a more concise solution of just a few lines.

I will keep trying to improve my knowledge so that I can produce more direct solutions in the future.

I heart that if our solution to a given dsa question is more than 20 lines or so, then there's probably a more optimal solution.

My solution was exactly 20 lines, but I definitely saw there were some more efficient solutions out there than mine. Let's keep working hard and trying to improve everyday!
