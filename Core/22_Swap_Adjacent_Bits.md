# Swap Adjacent Bits

[**Challenge Link**](https://app.codesignal.com/arcade/code-arcade/corner-of-0s-and-1s/dShYZZT4WmvpmfpgB)

**Prompt:** Implement the missing code, denoted by ellipses. You may not modify the pre-existing code.
You're given an arbitrary 32-bit integer n. Take its binary representation, split bits into it in pairs (bit number 0 and 1, bit number 2 and 3, etc.) and swap bits in each pair. Then return the result as a decimal number.

**Initial Thoughts:**

```
// It looks like we have to convert the number ’n’ into a binary string.

// Then we can split the string into an array that contains multiple arrays, forEach to loop through the 4 arrays, reversing the items in each, and then joining the 4 arrays together into a single string again before using parseInt to convert it back into a number.
```

**My Solution:**

```
// I ended up not being able to apply my solution because the code editor would only allow me to do a single line submit whereas I would need multiple lines to be able to implement my pseudocode.

// I tried to be clever to implement everything in only a single line, but ultimately I wasn't able to come up with a single line solution.
```

**Reflection:** The answer to the solution of course used bitwise operators:

```
function solution(n) {
  return ((n & 0xaaaaaaaa) >> 1) | ((n & 0x55555555) << 1);
}
```

Apparently `0xaaaaaaaa` is a hexadecimal value that represents `10101010101010101010101010101010` and `0x55555555` is a hexadecimal value that represents `01010101010101010101010101010101`.

The way the leading community submission works is it effectively uses `0xaaaaaaaa` and `0x55555555` as masks along with bitwise left shift `<<` and right shift `>>` operators and the `|` operation to swap odd and even index bits and then combine them.

Super clever, but not something I would've been able to realistically come up with.

If this were a DFS of BFS problem I'd probably invest more time to understand the nuances of this solution, but given how rare bitwise operators are used in interviews and my daily work I think this surface level understanding is enough for now.
