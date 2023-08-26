# reverseInParentheses

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-3/9DgaPsE2a7M6M2Hu6)

**Prompt:** Write a function that reverses characters in (possibly nested) parentheses in the input string.

Input strings will always be well-formed with matching ()s.

**Solution #1:**

```

function solution(inputString) {
  const resultArray = [];
  for (let i = 0; i < inputString.length; i += 1) {
    if (inputString[i] === "(") {
      const nestedCharacters = [];
      while (true) {
        i += 1;
        nestedCharacters.push(inputString[i]);
        if (inputString[i] === "(") {
          const doubleNestedCharacters = [];
          while (true) {
            i += 1;
            doubleNestedCharacters.push(inputString[i]);
            if (inputString[i] === ")") {
              doubleNestedCharacters.pop();
              resultArray.push(doubleNestedCharacters.reverse().join(""));
              break;
            }
          }
        }
        if (inputString[i] === ")") {
          nestedCharacters.pop();
          resultArray.push(nestedCharacters.reverse().join(""));
          break;
        }
      }
    } else {
      resultArray.push(inputString[i]);
    }
  }
  return resultArray.join("");
}

```

**Pseudocode #2:**

```
// First we need two variables, stringToBeReturned and stack.

// We then need to loop through the original inputString.

// As we're looping through the array we're looking for opening parenthisis. Once we find one, we push stringToBeReturned to stack. We then clear our stringToBeReturned.

// When we find A closing parenthisis, we get the previous value added to stack using stack.pop() and then concatenate the new reversed value to it (the current value would be whatever stringToBeReturned was).

// For cases that aren't parenthesis, we simply add the current letter to stringToBeReturned.

// When we finally finish looping through the entire string, we return stringToBeReturned as our answer.
```

**Solution #2:**

```

function solution(inputString) {
  const stack = [];
  let stringToBeReturned = "";

  for (let i = 0; i < inputString.length; i+=1) {
    if (inputString[i] === "(") {
      stack.push(stringToBeReturned);
      stringToBeReturned = "";
    } else if (inputString[i] === ")") {
      stringToBeReturned = stack.pop() + stringToBeReturned.split("").reverse().join("");
    } else {
      stringToBeReturned += inputString[i];
    }
  }
  return stringToBeReturned;
}
```

**Reflection:** I was almost able to solve this problem on my own, but I ran into some problems with the nested parentheses.

Throughout the rest of the day I spent some time looking at solutions, reading them, hand typing them line by line and analyzing them to understand them.

Then, I wrote pseudocode for the solution and forced myself to resolve the problem. Even after spending a lot of time with this problem and developing a logical understanding of the solution, it still doesn't feel very intuitive to me.

The thing I am happy about, however, is I feel like I really challenged myself today and exposed myself to a new more efficient way of solving this type of problem.
