# String Repeat

DESCRIPTION:

An isogram is a word that has no repeating letters, consecutive or non-consecutive. Implement a function that determines whether a string that contains only letters is an isogram. Assume the empty string is an isogram. Ignore letter case.

## Examples (input -> output)

```
"Dermatoglyphics" --> true
"aba" --> false
"moOse" --> false (ignore letter case)
```

## Given Code

```python
def is_isogram(string):
    #your code here
```

## Solution 1: Solving with sets

Sets eliminate any duplicates, so by putting the string in a set, we automatically remove any repeating characters. If there were duplicate characters in the string, the length of the set would be smaller than the original string, making the comparison return `False`. If there are no repeating characters, both lengths will be the same, so the function returns `True`.

```python
def is_isogram(string):
    return len(string) == len(set(string.lower()))
```

## Solution 2: Hashtable (dictionary) 

1. Create an empty dictionary to store characters as keys.
2. Loop through each character.
3. Check if the character is already in the dictionary.
4. If the character been seen before, that means it’s a duplicate, so return False.
5. If the character is not in the dictionary, add it. This marks the character as seen.
6. If the loop finishes without finding duplicates, return True:

```python
def is_isogram(string):
    
    seen = {}
    
    for char in string.lower():
        if char in seen:
            return False
        seen[char] = 1
    return True
```

[Codewars Kata](https://www.codewars.com/kata/57a0e5c372292dd76d000d7e/train/javascript)