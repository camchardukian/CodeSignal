# alphabeticShift

[**Challenge Link**](https://app.codesignal.com/arcade/intro/level-6/PWLT8GBrv9xXy4Dui)

**Prompt:** Given a string, your task is to replace each of its characters by the next one in the English alphabet; i.e. replace a with b, replace b with c, etc (z would be replaced by a).

**Initial Thoughts:**

```
// I think I should be able to solve this problem either using charCodeAt or by making a dictionary or another similar approach.
```

**Solution:**

```
function solution(inputString) {
  const dictionary = {
    a: "b",
    b: "c",
    c: "d",
    d: "e",
    e: "f",
    f: "g",
    g: "h",
    h: "i",
    i: "j",
    j: "k",
    k: "l",
    l: "m",
    m: "n",
    n: "o",
    o: "p",
    p: "q",
    q: "r",
    r: "s",
    s: "t",
    t: "u",
    u: "v",
    v: "w",
    w: "x",
    x: "y",
    y: "z",
    z: "a",
  };
  return inputString
    .split("")
    .map((letter) => dictionary[letter])
    .join("");
}
```

**Reflection:** Seems like my initial thoughts for this problem were spot on. My approach worked, otherwise returning 'a' if there was a 'z' character along with adding 1 to the charCode to all of the letters would have been another valid approach.
