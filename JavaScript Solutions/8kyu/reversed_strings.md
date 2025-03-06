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

## Solution

1. `split()` method will return the string to a list of its characters as elements
2. `reverse()` method  will reverse an array's elements
3. `join()` method concatenates all elements in an array to a string

```javascript
function solution(str){
  return str.split('').reverse().join('')
}
```

[Codewars Kata](https://www.codewars.com/kata/5168bb5dfe9a00b126000018/javascript)