---
title: Filters
description: 
published: true
date: 2022-07-27T15:27:04.612Z
tags: 
editor: markdown
dateCreated: 2022-05-02T19:46:23.699Z
---

#### Prerequisite Knowledge
- [OO Concepts](/ooConcepts)
- [Functional Programming](/functionalProgramming/functionalProgramming)

# Filter
A filter operation selects items from the input stream to pass on to the output stream based on some characteristic of the input stream element.

In the image below a filter is used to extract the elements of the original stream that have two syllables. The original stream contains the words bird,cat,dog,horse,chicken and rabbit. The resulting stream consists only of the two-syllable elements: chicken and rabbit. 

![illustration of the filtering described above.](/images/filterFunction.png)


The code to create the filtered stream is shown below.

```java
List<String> temp =
  strings.stream()
    .filter(s -> s.countSyllables().equals(2))
    .collect(Collectors.toList());   
```

### Boolean predicates

A lambda expression that assesses each element of the original stream must be passed to the filter method. The lambda expression must return `true` if the element should be part of the result stream and `false` otherwise.
This boolean lambda expression is called a predicate.

If the predicate returns true for an element of the input stream then that element is passed on to the output stream; otherwise it is not. 

The predicate for the filter shown above is `s -> s.countSyllables().equals(2)`. `s` in this case is the next element of the stream. `countSyllables()` is a method for that element type (that the programmer has written) that returns the number of syllables in the word. The entire lambda expression will return true if the number of syllables equals 2 and false otherwise.

One simplified way to "read" a lambda expression is to treat the `->` operator as a condition. The expression above can be thought of semantically as "Given an element `s`, execute the countSyllables method, and if there are 2 syllables return true".
