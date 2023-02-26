---
title: Maps
description: 
published: 1
date: 2022-08-17T20:15:27.461Z
tags: 
editor: markdown
dateCreated: 2022-08-17T18:14:04.965Z
---

#### Prerequisite Knowledge
- [OO Concepts](/ooConcepts)
- [Functional Programming](/functionalProgramming/functionalProgramming)

# Map

The `map()` method of a `Stream` is used to create a new stream based on some characteristic of the existing stream. Map is a common type of functional operation, that inspects items from the input stream, applies a conversion to the item, and puts the converted items in the output stream.

For example, the image below shows two collections. The first is a collection of strings and the second is a collection of integers.  The map between them is that the second collection represents the string length of the elements in the first collection.

![illustration of two collections, a colection of strings, and a mapped collection of integers, where each element  represents the length of the matching string in the first collection.](/images/mapFunction.png)


The type of the objects in the output stream is often (but not necessarily) different from the type in the input stream. The code to produce the output stream shown in the image can be seen below.

```java
strings.stream().map(element -> element.length())
```

The resulting output stream could be printed, put into a different collection, used in some other calculation (like finding the average length of strings) or stored persistently.

The additional code below shows how it could be stored into a separate list.


```java
List<String> temp =
  strings.stream()
    .map(element -> element.length())
    .collect(Collectors.toList());   
```



