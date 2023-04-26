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
- Faster?
- Less memory-intensive?
- More readable?

## Why not use timers?
## The Problem with Time
- Different machines will record different times
- The same machine will record different times
- For fast algorithims, speed measurements may not be precise enough?

## If not time, then what?
Rather than counting seconds, which are so variable...
Let us count the number of simple operations the computer has to perform!

## Counting Operations
```
function addUpTo(n) {
  return n * (n + 1) / 2;
}
```
1 Multiplication
1 Addition
1 Division
3 Simple oprations regardless on the size of n
# vs.
```
function addUpTo(n) {
  let total = 0;
  for (let i = 1; i <= n; i++) {
    total += i;
  }
  return total;
}
```
n additions
n assignments
n additions and assignments
1 assignment
1 assignment
n comparisons
## Counting is hard!
Depending on what we count, the number of operations can be as low as 2n or as high as 5n + 2 
But regardless of the exact number, the number of operations grows roughly proportionally with n
If n doubles, the number of operations will also roughly double

## Introducing....Big O
Big O Notation is a way to formalize fuzzy counting

It allows us to talk formally about how the runtime of an algorithm grows as the inputs grow

We won't care about the details, only the trends

## Big O Definition
We say that an algorithm is O(f(n)) if the number of simple operations the computer has to do is eventually less than a constant times f(n), as n increases

f(n) could be linear (f(n) = n)
f(n) could be quadratic (f(n) = n  )
f(n) could be constant (f(n) = 1)
f(n) could be something entirely different!

### Example
-|-
```
Example
function addUpTo(n) {
  return n * (n + 1) / 2;
}
``` | Always 3 operations O(1)
```
function addUpTo(n) {
  let total = 0;
  for (let i = 1; i <= n; i++) {
    total += i;
  }
  return total;
}
``` | Number of operations is (eventually) bounded by a multiple of n (say, 10n) O(n)

### Another Example
-|-
```
function countUpAndDown(n) {
  console.log("Going up!");
  for (let i = 0; i < n; i++) {
    console.log(i);
  }
  console.log("At the top!\nGoing down...");
  for (let j = n - 1; j >= 0; j--) {
    console.log(j);
  }
  console.log("Back down. Bye!");
}
``` | Number of operations is (eventually) bounded by a multiple of n (say, 10n) O(n)

### Moar Examplez
-|-
```
function printAllPairs(n) {
  for (var i = 0; i < n; i++) {
    for (var j = 0; j < n; j++) {
      console.log(i, j);
    }
  }
}
``` | O(n) operation inside of an O(n) operation. O(n * n)

## Simplifying Big O Expressions
When determining the time complexity of an algorithm, there are some helpful rule of thumbs for big O expressions.
These rules of thumb are consequences of the definition of big O notation.

## Contants Do Not Matter

## Recap
- To analyze the performance of an algorithm, we use Big O Notation.
- Big O Notation can give us a high level understanding of the time or space complexity of an algorithim.
- Big O Notation does not care about precision, only about general trends (linear? quadratic? constant?)
- The time or space complexity (as measured by Big O) depends only on the algorithm, not the hardware used to run the algorithm.
- Big O Notation is everywhere, so get lots of practice!