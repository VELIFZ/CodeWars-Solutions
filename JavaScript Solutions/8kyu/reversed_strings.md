# Reversed Strings

DESCRIPTION:

Complete the solution so that it reverses the string passed into it.

```
'world'  =>  'dlrow'
'word'   =>  'drow'
```

## Given Code

```javascript
function solution(str){
  
}
```

## Solution 1: Using JS built-in methods

1. `split()` method will return the string to a list of its characters as elements
2. `reverse()` method  will reverse an array's elements
3. `join()` method concatenates all elements in an array to a string

```javascript
function solution(str){
  return str.split('').reverse().join('')
}
```

## Solution 2: Using Two Pointers Approach

1. Convert the string into an array since JavaScript strings are immutable.
2. Set up two pointers. One starting from the beginning (`left`) and one starting from the end (`right`).
3. Loop through the array until the `right` pointer is no longer greater than the `left` pointer.
4. Swap the values at the left and right indexes.
5. Move the pointers. Increase left (`left++`) and ecrease right (`right--`).
6. Once all elements are reversed, convert the array back into a string.

```javascript
function solution(str){
  let arr = str.split("");
  let left = 0;
  let right = str.length -1;

  while (left < right) {
    [arr[left], arr[right]] = [arr[right], arr[left]];

    left ++;
    right--;
  }
  return arr.join("")
}
```

Two-pointer approach is better because:

- More memory-efficient (O(1)):
  It reverses the string in place instead of creating multiple arrays.
- Unlike str.split("").reverse().join(""), which creates three arrays (split, reverse, join), this method only modifies one array.
- Faster for large inputs (O(n)):
  Since only iterate through half of the array, it avoids unnecessary extra operations.
- More control over swapping.

[Codewars Kata](https://www.codewars.com/kata/5168bb5dfe9a00b126000018/javascript)