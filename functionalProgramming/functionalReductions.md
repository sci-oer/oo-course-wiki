---
title: Reductions
description: 
published: 1
date: 2022-08-17T20:15:46.087Z
tags: 
editor: markdown
dateCreated: 2022-08-17T18:14:09.887Z
---

#### Prerequisite Knowledge
- [OO Concepts](/ooConcepts)
- [Functional Programming](/functionalProgramming/functionalProgramming)

# Reductions

A reduction produces a single value from some sort of calculation involving each of the elements of a stream. For example, one common reduction in an list of numbers is an average. The image below shows the result of a reduction that returns the number of occurences of the letter `c` in the stream.

![illustration of the results of reducing a stream containing several words to a count of the number of times the letter c occurs in the stream.](/images/functionalReduction.png)


The `reduce` method is slightly more complex to use than either `map` or `filter` but it is extremely useful. The purpose of the method is to ‘collapse’ a multi-element stream to a single ‘value’. `reduce` takes two parameters: A variable of the type that the reduction is expected to produce and a lambda expression.  
  `reduce(variable, (accumulator, element) -> accumulator + resultFromSomeMethod)`

**The first parameter** is a starting value for the final result.  In the case of a count that will often be zero, but it can be any starting value desired.

**The second paramter** is a **two** parameter lambda expression.  The first parameter to the lambda expression is an internal variable used to accumulate the reduction as it is applied to each element.  The second paramter is an element of the stream.

The expression part of the lambda details how to reduce the element to a composite part of the overall reduction.

The lambda expression for the reduction shown in the image could be:
`(accumulator, element) -> accumulator + element.countCharacter('c')`

The lambda expression has two parameters, `accumulator` and `element`. The reduction portion of the lambda indicates that the `countCharacter()` method should be called for the element and the return value added to the accumulator.

The code shown below would perform the reduction shown in the image.  

```java
int startVal = 0;
int numChar =
  strings.stream()
    .reduce(startVal,(accumulator, element) -> accumulator + element.countCharacter('c'));
```



