# Logic

[Return to the Basic Python mainpage](https://luger-lab.github.io/coding-tutorials/basic_python/)

## [&larr; Back to Loops](https://luger-lab.github.io/coding-tutorials/basic_python/loops/)

## Description
There are many times when coding that you'll want to make a logic check. In Python there are a few types of logic checks: boolean, is/is not, and comparisons.

## Boolean
Boolean means True or False, in Python these are denoted as capitalized `True` or `False` and are not strings, so do not need quotes. In fact, using quotes will return a string, not a boolean. You can set variables equal to booleans or return them after logical operations.

## is/is not
`is` compares whether or not a variable refer to the same memory reference. It returns `True` if two variables reference the same memory location.
```
a = "happy"
b = "unhappy"
c = a
a is c
True
```
You can check the memory location using `id`.
```
id(a)
140241117068272
id(c)
140241117068272
```
`is not` is the opposite of is and will return `True` if the variables reference different memory loactions.
```
c is not b
True
```
## Value comparisons


## If statements

## [Back to Coding tutorials mainpage &rarr;](https://luger-lab.github.io/coding-tutorials/)
