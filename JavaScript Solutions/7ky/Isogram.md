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

```javascript
function isIsogram(str){
  //...
}
```

## Solution 1: Solving with sets

Sets remove duplicates, so when we put the string in a set, any repeating characters automatically get eliminated. If the string had duplicate characters, the set's size will be smaller than the original string's length, making the comparison return `false`. If there were no duplicates, both lengths will be the same, so the function returns `true`.

- This method

```javascript
function isIsogram(str){
	return str.length === new Set(str.toUpperCase()).size ;
}
```

## Solution 2: Objects 

1. Create an empty object to store characters as keys to track if they have been seen before.
2. Loop through each character in the string.
3. Check if the character already exists in the object.
4. If yes, it means the character is a duplicate → return false immediately.
5. If no, add the character to object.
6. If the loop finishes without finding duplicates, return true.


```javascript
function isIsogram(str){
    let seen = {};
    
    for (let char of str.toUpperCase()) {
        if (seen[char]) {
                return false;
        }
        seen[char] = 1;
    }
    return true;
}
```

[Codewars Kata](https://www.codewars.com/kata/57a0e5c372292dd76d000d7e/train/javascript)