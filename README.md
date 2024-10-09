# LEETCODE-Strings-921
Let's dry run the `minAddToMakeValid` function with a sample input to better understand how it works.

### Problem:
The goal of the function is to determine the minimum number of parentheses that must be added to make a string of parentheses valid (balanced).

### Logic:
- `l`: Counts unmatched opening parentheses `(`.
- `r`: Counts unmatched closing parentheses `)`.

### Code Breakdown:
1. Traverse the string `s` character by character.
2. If the character is an opening parenthesis `(`, increment `l`.
3. If the character is a closing parenthesis `)`, check:
   - If `l` is greater than 0, meaning there are unmatched opening parentheses, decrement `l` (to balance a pair).
   - If `l` is 0, increment `r` (indicating an unmatched closing parenthesis).
4. After the loop, the sum `l + r` gives the total number of unmatched parentheses that need to be added to make the string valid.

### Dry Run:

Let's dry run with the input `s = "())("`.

| Step | Char | `l` (unmatched `(`) | `r` (unmatched `)`) | Action                              |
|------|------|---------------------|---------------------|-------------------------------------|
| 1    | `(`  | 1                   | 0                   | Increment `l` (found an opening `(`)|
| 2    | `)`  | 0                   | 0                   | Decrement `l` (found a matching pair)|
| 3    | `)`  | 0                   | 1                   | Increment `r` (unmatched closing `)`)|
| 4    | `(`  | 1                   | 1                   | Increment `l` (unmatched opening `(`)|

### Result:
- At the end of the loop, `l = 1` (unmatched opening `(`) and `r = 1` (unmatched closing `)`).
- The result is `l + r = 1 + 1 = 2`.

So, we need to add 2 parentheses to make the string valid.
