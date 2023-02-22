---
title: Functional Collection Processing
description: 
published: true
date: 2022-08-30T14:32:23.793Z
tags: 
editor: markdown
dateCreated: 2022-05-02T19:46:18.765Z
---

#### Prerequisite Knowledge
- [OO Concepts](/ooConcepts)
- [Functional Programming](/functionalProgramming/functionalProgramming)
# Functional Collection Processing
Java provides features that enable a programmer to create functional solutions when appropriate. In particular the ability to process the elements of a collection using a functional approach increases readability and helps to ensure that side effects of the processing don't occur. One of the advantages of functional processing of collections is that parallel processing is easily accomplished which makes processing large collections much faster.

A collection in Java has an inherited method, `stream()` that returns a version of the collection as a class, [`Stream`](http://localhost:8000/docs/api/java.base/java/util/stream/Stream.html), that is designed for functional processing.   
A collection can be converted to a stream and then processed in a functional pipeline. Typical operations on a collection are 
[Filters](/functionalProgramming/functionalFilters),  [Maps](/functionalProgramming/functionalMaps), and  [Reductions](/functionalProgramming/functionalReductions). 


## OO and Procedural Collection Processing

Pseudocode for processing a collection procedurally is shown below.  It relies on a loop that can detect the end of the collection.
```
loop (for each element in the collection):
    get one element;
    do something with the element;
end loop
```

In Java we can use the enhanced for loop to step through each element of most collection types.
```java
for(Record record : allStudents) {
    applyForBursary(record);
}
```
## Functional Collection Processing

A collection is processed functionally by calling a function that will walk through the collection and inspect each element. That function then executes the code to handle each element. 

```
collection.doThisForEachElement(some code or method here);
```
Java allows us to define a lamba express which can be applied to each element in the collection. It also provides a `forEach()` method that handles walking through the collection.

```java
allStudents.forEach(record -> applyForBursary(record));
```
The lambda expression that is passed to the forEach method as a parameter contains the code that will be applied to each element.


## Collection processing example

This example may make more sense after you have explored the wiki pages about [Filters](/functionalProgramming/functionalFilters)m  [Maps](/functionalProgramming/functionalMaps), and [Reductions](/functionalProgramming/functionalReductions).

Suppose we have an ArrayList of strings. We want to print out only the strings that end with the two letters `ly`.

The first solution uses an intermediate variable, `temp`, to store a list of strings and then calls the `forEach` method to print out that string.

The `filter()` method of the stream is called to select only the elements of the stream that end in `ly` and return a new stream that contains only the desired elements. The `collect()` method is used to create a new collection of the selected elements. The parameter to that method controls the type of collection returned (in this case a `List<String>`).

```java
List<String> temp = strings.stream()
	.filter(name ->name.endsWith(“ly”))
  .collect(Collectors.toList());
    
 //printing here
temp.forEach(s->System.out.println(s));
```

The code snippet below does exactly the same thing without the intermediate variable. Assume that `ArrayList<String> strings` has been initialized with a set of string values.

```java
strings.stream()
	.filter(name -> 
		name.endsWith(“ly”))
		.collect(Collectors.toList())
		.forEach(
			s->System.out.println(s));
```

#### Recorded Lecture
[Processing Collections as Streams](http://localhost:8000/lectures/functionalProgramming/CollectionProcessing/)

#### Practice 
 - Tutorial: [collection processing](http://localhost:8888/lab/tree/tutorials/functionalProgramming/collectionProcessing.ipynb)

