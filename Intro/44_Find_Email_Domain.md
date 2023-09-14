# Find Email Domain

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-10/TXFLopNcCNbJLQivP)

**Prompt:** An email address such as "John.Smith@example.com" is made up of a local part ("John.Smith"), an "@" symbol, then a domain part ("example.com").

The domain name part of an email address may only consist of letters, digits, hyphens and dots. The local part, however, also allows a lot of different special characters. Here you can look at several examples of correct and incorrect email addresses.

Given a valid email address, find its domain part.

**Initial Thoughts:**

```
// My first thought is we just return everything after the "@" symbol, but that seems too simple so let's think about some cases to see where that wouldn't work.

// The only thing I think that may trip us up is that the local part could also have an "@" symbol.

// For that reason, I think we need to find the last "@" character and return everything after that (because the domain part of the email address cannot contain multiple @ characters).

// To do that, the solution is to reverse the string, use indexOf to find the first occurence of "@", and then use the slice method to return 0, up until the indexOf value.
```

**Solution:**

```
function solution(address) {
    const finalAtCharacterIndex = address.split("").reverse().indexOf("@");
    return address.slice(address.length - finalAtCharacterIndex)
}
```

**Reflection:** I learned a couple things while working through this problem. The first is that JavaScript has a `lastIndexOf` method.

I also admired the cleverness of this solution:

```
function solution(address) {
    return address.split('@').pop()
}
```
