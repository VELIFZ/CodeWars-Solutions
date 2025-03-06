# Remove String Spaces

DESCRIPTION:

Write a function that removes the spaces from the string, then return the resultant string.

## Examples (input -> output)

```
"8 j 8   mBliB8g  imjB8B8  jl  B" -> "8j8mBliB8gimjB8B8jlB"
"8 8 Bi fk8h B 8 BB8B B B  B888 c hl8 BhB fd" -> "88Bifk8hB8BB8BBBB888chl8BhBfd"
"8aaaaa dddd r     " -> "8aaaaaddddr"
```

## Given Code

```javascript
function noSpace(x){

}
```

## Solution 1: Using `split()` and `join()` Methods

Split the string at each space (don't forget to include a space in .split()), then join the parts back together without spaces.

```javascript
function noSpace(x){
    return x.split(' ').join('')
}
```

## Solution 2: Using `replace()` and minimal Regex

In JavaScript, `.replace()` only replaces the first occurrence of the charater. If you want to remove all spaces:
1. / / matches a space character.
2. g makes it global, so it matches all spaces.
3. '' replaces all spaces with nothing (removes them).

```javascript
function noSpace(x){
    return x.replace(/ /g, '')
}
```

## Solution 3: Using `replaceAll()`

`string.replaceAll(searchValue, newValue)`

```javascript
function noSpace(x){
    return x.replaceAll(' ', '')
}
```

[Codewars Kata](https://www.codewars.com/kata/57eae20f5500ad98e50002c5/javascript)
