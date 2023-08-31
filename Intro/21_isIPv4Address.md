# isIPv4Address

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-5/veW5xJednTy4qcjso)

**Prompt:** An IP address is a numerical label assigned to each device (e.g., computer, printer) participating in a computer network that uses the Internet Protocol for communication. There are two versions of the Internet protocol, and thus two versions of addresses. One of them is the IPv4 address.

Given a string, find out if it satisfies the IPv4 address naming rules.

**Initial thoughts:**

```
// The first thing I'm thinking is that this problem would be the perfect candidate for a regex solution.

// Unfortunately, while I'm comfortable using regex in production apps, I'm not as confident in my ability to use regex in a whiteboard setting without being able to reference any external resources.

// I think the regex would be something like /[0-255]\.[0-255]\.[0-255]\.[0-255]/ but maybe my syntax is off by a bit without checking the internet.

// Without regex, I think we could also solve this problem by using .split(".").

// We could then check that the resulting array had a length of 4, and then loop through each item and check that it doesn't have any leading zeros, and that the item as a number is between 0 and 255.
```

**Solution:**

```
function solution(inputString) {
    const inputStringAsArray = inputString.split(".");
    if (inputStringAsArray.length !== 4) {
        return false;
    }
    for (let i = 0; i < inputStringAsArray.length; i++) {
        if (0 > parseInt(inputStringAsArray[i]) || parseInt(inputStringAsArray[i]) > 255 || !inputStringAsArray[i] ) {
            return false;
        }
        if (isNaN(inputStringAsArray[i])) {
            return false;
        }
        let leadingZeros = 0;
        let hadNonZeroDigitAlready = false;

        for (let ii = 0; ii < inputStringAsArray[i].length; ii++) {
                if (leadingZeros) {
                    return false;
                }
            if (inputStringAsArray[i][ii] === "0" && !hadNonZeroDigitAlready) {
                leadingZeros +=1;
                continue;
            }
            hadNonZeroDigitAlready = true;
        }
    }
    return true;
}
```

**Reflection:** My initial thoughts were able to get me started on a path that eventually led to a solution, but my final solution was really lengthy and even while writing it I felt there had to be a better way of solving this problem (even if I would only accept a non-regex solution).

Unfortunately, it seems this problem must have been updated recently because most of JS solutions didn't pass the test cases because they didn't account for leading zeros like I did, and the ones that did pass the test cases used regex.

I guess the takeaway here is that I that I should get more comfortable using regex live in high pressure situations straight off the dome ;)
