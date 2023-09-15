# Is MAC48 Address?

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-10/HJ2thsvjL25iCvvdm)

**Prompt:** A media access control address (MAC address) is a unique identifier assigned to network interfaces for communications on the physical network segment.

The standard (IEEE 802) format for printing MAC-48 addresses in human-friendly form is six groups of two hexadecimal digits (0 to 9 or A to F), separated by hyphens (e.g. 01-23-45-67-89-AB).

Your task is to check by given string inputString whether it corresponds to MAC-48 address or not.

**Initial Thoughts:**

```
// I think all I need to do to solve this problem is create a regular expression that checks that we have six groups of hexadecimal digits with two characters each.
```

**Solution:**

```
function solution(inputString) {
  const regex = /^([0-9A-F]{2}-){5}[0-9A-F]{2}$/;
  return regex.test(inputString);
}
```

**Reflection:** The only thing that wasn't straightforward about this problem for me was trying to remember the regex syntax for repeating characters.

I couldn't remember the syntax so I had to search it. Everything else was easy enough.
