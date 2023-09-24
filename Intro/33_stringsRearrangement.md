# stringsRearrangement

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-7/PTWhv2oWqd6p4AHB9)

**Prompt:** Given an array of equal-length strings, you'd like to know if it's possible to rearrange the order of the elements in such a way that each consecutive pair of strings differ by exactly one character. Return true if it's possible, and false if not.

Note: You're only rearranging the order of the strings, not the order of the letters within the strings!

**Initial Thoughts:**

```
// We need to find all possible permutations of the given input array.

// Since we know that all strings will be equal length, we can then use a nested for loop to compare each string to the previous string and use a diffCount variable to ensure each previousString and currentString are different by exactly one character.
```

**My Solution:**

```
function solution(inputArray) {
  const permutations = (elements) => {
    if (elements.length === 0) return [[]];
    const firstEl = elements[0];
    const rest = elements.slice(1);
    const permsWithoutFirstEl = permutations(rest);
    const allPermutations = [];
    permsWithoutFirstEl.forEach((perm) => {
      for (let i = 0; i <= perm.length; i++) {
        const permWithFirst = [...perm.slice(0, i), firstEl, ...perm.slice(i)];
        allPermutations.push(permWithFirst);
      }
    });
    return allPermutations;
  };

  const isDifferenceCountOne = (string1, string2) => {
    let differenceCount = 0;
    for (let i = 0; i < string1.length; i++) {
      if (string1[i] !== string2[i]) {
        differenceCount++;
      }
    }
    return differenceCount === 1;
  };

  const allPossiblePermutations = permutations(inputArray);

  for (let i = 0; i < allPossiblePermutations.length; i++) {
    for (let ii = 1; ii < allPossiblePermutations[i].length; ii++) {
      if (
        !isDifferenceCountOne(
          allPossiblePermutations[i][ii],
          allPossiblePermutations[i][ii - 1]
        )
      ) {
        break;
      } else if (ii === allPossiblePermutations[i].length - 1) {
        return true;
      }
    }
  }
  return false;
}
```

**Reflection:** While my 'initial thoughts' may have made this problem sound simple, it's one of, if not THE most challenging dsa problem I've solved thus far.

While it took several hours to solve, I picked up so much great knowledge along the way.

I strengthened my knowledge of recursion, I learned about factorials, and I learned about permutations and the difference between permutations and combinations.

I see that my solution was pretty good overall. There was one community submission I liked even better:

```
function solution(a) {
  for (let i = 0; i < a.length; i++) {
    let remaining = findNext(a[i], a);
    if (remaining.length === 0) return true;
  }
  return false;
}

function findNext(current, a) {
  if (a.length === 0) return a;
  for (let i = 0; i < a.length; i++) {
    if (differsByOneChar(current, a[i])) {
      let remaining = findNext(a[i], a.slice(0, i).concat(a.slice(i+1)));
      if (remaining.length === 0) return remaining;
    }
  }
  return a;
}

function differsByOneChar(s1, s2) {
  let mismatches = 0;
  for (let i = 0; i < s1.length; i++) {
    if (s1[i] !== s2[i]) mismatches++;
    if (mismatches > 1) break;
  }
  return mismatches === 1;
}
```

but I'm happy to have learned so much while solving this problem. I gained a lot of confidence that if I stay the course I can continue learning more and eventually be able to tackle leetcode mediums and even leetcode hards!
