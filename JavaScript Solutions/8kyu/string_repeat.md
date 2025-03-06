# String Repeat
DESCRIPTION:

Write a function that accepts a non-negative integer `n` and a string `s` as parameters, and returns a string of `s` repeated exactly `n` times.

## Examples (input -> output)

```
6, "I"     -> "IIIIII"
5, "Hello" -> "HelloHelloHelloHelloHello"
```

## Given Code

```javascript
function repeatStr (n, s) {
    return '';
}
```

## Solution 1: Using `.repeat()` Method

```javascript
function repeatStr (n, s) {
    return s.repeat(n);
}
```

## Solution 2: Using a For Loop

If you don't know the `.repeat()` method, you can use a for loop.

1. Create an empty string to store the final repeating string.
2. Run the loop `n` times.
3. Add `s` to the result with each iteration.
4. Return the new string.

```javascript
function repeatStr (n, s) {
    let result = '';
    
    for (let i = 0; i < n; i++) {
        result += s;
    }
    return result;
}
```

[Codewars Kata](https://www.codewars.com/kata/57a0e5c372292dd76d000d7e/train/javascript)