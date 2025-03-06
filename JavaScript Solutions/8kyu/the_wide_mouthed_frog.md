# The Wide-Mouthed frog!

DESCRIPTION:

The wide-mouth frog is particularly interested in the eating habits of other creatures.

He just can't stop asking the creatures he encounters what they like to eat. But, then he meets the alligator who just LOVES to eat wide-mouthed frogs!

When he meets the alligator, it then makes a tiny mouth.

Your goal in this kata is to create complete the mouth_size method this method takes one argument animal which corresponds to the animal encountered by the frog. If this one is an alligator (case-insensitive) return small otherwise return wide.

## Given Code

```javascript
function mouthSize(animal) {
  // code here
}
```

## Solution 1: Using an if Statement

```javascript
function mouthSize(animal) {
    if (animal.toLowerCase() === 'alligator')
        return 'small';
    return 'wide';
}
```

## Solution 2: Using a Ternary Operator

Syntax: `condition ? value_if_true : value_if_false`

If animal equals 'alligator', it returns `"small"`, otherwise `"wide"`.

```javascript
function mouthSize(animal) {
    return animal.toLowerCase() == 'alligator' ? 'small' : 'wide';
}
```
[Codewars Kata](https://www.codewars.com/kata/57ec8bd8f670e9a47a000f89/train/javascript)