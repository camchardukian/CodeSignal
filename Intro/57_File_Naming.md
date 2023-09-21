# File Naming

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-12/sqZ9qDTFHXBNrQeLC)

**Prompt:**
You are given an array of strings names representing filenames. The array is sorted in order of file creation, such that names[i] represents the name of a file created before names[i+1] and after names[i-1] (assume 0-based indexing). Because all files must have unique names, files created later with the same name as a file created earlier should have an additional (k) suffix in their names, where k is the smallest positive integer (starting from 1) that does not appear in previous file names.

Your task is to iterate through all elements of names (from left to right) and update all filenames based on the above. Return an array of proper filenames.

**Initial Thoughts:**

```
// I think what we need to do is loop through the array, and at each index check to see if the current value (including the suffix) has an indexOf lower than the current index.

// If so, we append the current suffix + 1. The problem, however, is what do we do with items that already have a suffix before our formatting?

// Maybe we apply a regex that checks for any items that have a suffix pre-processing and add a doNotModify flag to them?

// No, here's a better idea. For each item we will do a regex match on that item. For all items that match, we will then apply the suffixes in order (1), (2), etc.

// I don't know how to re-insert the items at the correct indexes, but I think the regex match will give me the index each item is located at so maybe I can use that.
```

**My First Attempt Solution:**

```
function solution(names) {
  const namesWithSuffixes = [...names];
  for (let i = 0; i < namesWithSuffixes.length - 1; i++) {
    let suffixNumber = 1;
    for (let ii = i + 1; ii < namesWithSuffixes.length; ii++) {
      if (namesWithSuffixes[ii] === namesWithSuffixes[i]) {
        namesWithSuffixes[ii] = namesWithSuffixes[i] + `(${suffixNumber})`;
        suffixNumber += 1;
      }
    }
  }
  return namesWithSuffixes;
}
```

**The Actual Solution:**

```

const solution = names => {
    const used = {};
    return names.map(name => {
        let newName = name;

        while (used[newName]) {
            newName = `${name}(${used[name]++})`;
        }
        used[newName] = 1;
        return newName;
    });
};
```

**Reflection:** Seems the difficulty level has risen dramatically the last few problems. I was able to solve 4/6 test cases, but I had to review the community solutions to find a solution that solved all of the test cases.

It seems the key was to keep track of items we had already modified rather than only trying to rename future items. The optimal solution also did a good job of being O(n) complexity rather than trying to use nested for loops like I did.

Once I saw myself using nested for loops I figured there was probably a better solution. Hopefully tomorrow I can get back to solving problems without needing hints.
