# areEquallyStrong

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-5/g6dc9KJyxmFjB98dL)

**Prompt:** Call two arms equally strong if the heaviest weights they each are able to lift are equal.

Call two people equally strong if their strongest arms are equally strong (the strongest arm can be both the right and the left), and so are their weakest arms.

Given your and your friend's arms' lifting capabilities find out if you two are equally strong.

**Pseudocode:**

```
// This question seems too easy. I think I'm missing something.

// My first instinct is that we just need to check if our strong hand is equal to their strong hand, and our weak hand is equal to their weak hand.
```

**Solution:**

```
function solution(yourLeft, yourRight, friendsLeft, friendsRight) {
    const yourStrongArm = yourLeft >= yourRight ? yourLeft : yourRight;
    const yourWeakArm = yourLeft <= yourRight ? yourLeft : yourRight;
    const friendsStrongArm = friendsLeft >= friendsRight ? friendsLeft : friendsRight;
    const friendsWeakArm = friendsLeft <= friendsRight ? friendsLeft : friendsRight;
    return yourStrongArm === friendsStrongArm && yourWeakArm === friendsWeakArm
}
```

**Reflection:** I found this problem really easy to solve after carefully reading the constraints,
and expected inputs and outputs inside the test cases.

I think that was the key, to just read carefully before coding, and if one did that the coding shouldn't have been difficult.

After looking at other solutions I didn't see any meaningful improvements I could make and saw my solution was competitive with any of the other CodeSignal community submissions.
