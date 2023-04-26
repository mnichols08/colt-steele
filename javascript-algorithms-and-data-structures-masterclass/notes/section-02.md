# Big O Notation
## Objectives:
- Motivate the need for something like Big O Notation
- Describe what Big O Notation is
- Simplify Big O Expressions
- Define "time complexity" and "space complexity"
- Evaluate the time complexity and space complexity of different algorithms using Big O Notation
- Descrie what a logarithm is

## What is the Idea Here?
Imagine we have multiple implementations of the same function.
How can we determine which one is the best?
"Write a function that accepts a string input and returns a reversed copy"
`const revStr = str => str.reverse()`

## Who Cares?
- It is important to have a precise vocabulary to talk about how our code performs
- Useful for discussing trade-offs between differen approaches
- When your code slows down or crashes, identifying parts of the code that are inefficient can help us find pain points in our applications.
- Less important: it comes up in interviews!

## An Example
Suppose that we want to write a function that calculates the sum of all numbers from 1 up to (and including) some number n.
```
function addUpTo(n) {
  let total = 0;
  for (let i = 1; i <= n; i++) {
    total += i;
  }
  return total;
}
```
or
```
function addUpTo(n) {
  return n * (n + 1) / 2;
}
```
### Which one is better?

## ZOMG WUT
`addUpTo(n) = 1 + 2 + 3 + ... + (n - 1) + n`
`addUpTo(n) = n + (n - 1) + (n - 2) + ... + 2 + 1` + `addUpTo(n) = (n + 1) + (n + 1) + (n + 1) + ... + (n + 1) + (n + 1)`
=
`2addUpTo(n) = n * (n + 1)`
`addUpTo(n) = n(n + 1) / 2`

## So What does "better" even mean?
