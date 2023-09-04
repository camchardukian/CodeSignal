# variableName

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-6/6Wv4WsrsMJ8Y2Fwno)

**Prompt:** Correct variable names consist only of English letters, digits and underscores and they can't start with a digit.

Check if the given string is a correct variable name.

**Initial thoughts:**

```
// I feel like this problem is the perfect candidate for regEx. The only problem, is if I encountered this problem in an interview situation I may not know the exact syntax I should use, but let's give it a go.
```

**Solution:**

```
function solution(name) {
    const regEx = /^[a-zA-Z_][a-zA-Z0-9_]*$/;
return regEx.test(name)
}
```

**Reflection:** I was write that using regEx would be the best approach to this problem. I had to look up some regEx stuff as my original syntax before referencing documentation (/^[a-z|_]\*[a-z|A-Z|0-9]/) was a bit off, but I was able to produce a working answer with a little bit of research.
