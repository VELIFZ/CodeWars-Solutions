# Shortest Word

DESCRIPTION:

Simple, given a string of words, return the length of the shortest word(s).

String will never be empty and you do not need to account for different data types.

## Given Code

```python
def find_short(s):
    # your code here
    return l # l: shortest word length
```

## Solution 1: Using map() and split() with Lazy Evaluation

  `map(function, iterable)` applies a function to each item in an iterable.
  1. `split()` creates a list of words from the string.
  2. `map(len, s.split())` computes each word’s length one by one, without storing to a separate list. (`len` is the function, and `s.split()` is the iterable)
  3. `min()` finds the shortest word length.

```python
def find_short(s):
    return min(map(len, s.split()))
```

Why this approach?
- Memory Efficient: `map(len, s.split())` does not create a list of lengths. Instead, it generates each length one at a time, passing it directly to `min()`.
- Lazy evaluation:
    - Processes one item at a time instead of computing everything at once and storing it in memory. 
    - This saves memory and makes processing more efficient.
- Time Compexity: O(n) + O(k) ≈ O(n) (since k ≤ n, simplifies to O(n))
    - split() scans the string once (O(n)).
    - map(len, s.split()) processes words on the fly (O(k)).
    - min() finds the smallest length (O(k)).
- Space Conmplexty: O(k) (minimal extra space)
    - split() creates a list of words (O(k)).
    - No extra list is created for word lengths.

## Solution 2: Using Manuel Iteration


1. Set `min_length` to `len(s)`, since the longest possible word is the full string if there's only one word (non-empty). (Could use `float('inf')` for unknown ranges.)
2. Set `current_length `to `0` to track each word's length while looping through the string.
3. Loop through each character in the string and check:
    - If it's not a space, add `1` to `current_length`.
    - If it's a space and `current_length` is greater than `0`, update `min_length` (since looping a word just finished) and reset `current_length` to `0` again.
4. Finallt check if there's no space after the last word, the loop ends without updating `min_length`, so check `current_length` one last time to make sure the last word is counted.
5. Return `min_length`, which now holds the shortest word length.

```python
def find_short(s):
    min_length = len(s)
    current_length = 0

    for char in s:
        if char != ' ':
            current_length += 1
        else:
            if current_length > 0:
                min_length = min(min_length, current_length)
                current_length = 0 

    min_length = min(min_length, current_length) 
    
    return min_length
```

Why use manuel iteration?
- Better control over the process.
- O(1) space complexity since no extra lists are used.
- Efficient O(n) time complexity (single pass through the string). 

[Codewars Kata](https://www.codewars.com/kata/57cebe1dc6fdc20c57000ac9/train/python)