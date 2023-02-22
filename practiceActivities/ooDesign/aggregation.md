---
title: Objects composed of other Objects
description: 
published: true
date: 2022-05-18T18:42:43.242Z
tags: 
editor: markdown
dateCreated: 2022-05-02T19:53:10.970Z
---

# Objects Composed of Other Objects

# Practice Activities for [Objects by Aggregation](/ooDesign/aggregation)



### Self Study Questions
1. Aggregation is effected by?
<details>
<summary>click here for one possible answer</summary>
  
Composing classes by using other classes as composite parts.
</details>

2. An aggregation relationship can be described using which  words?
<details>
<summary>click here for one possible answer</summary>
  
**has-a**. 
  Example: A `Car` **has-a** `Driver`.
</details>

3. Composition is what kind of a relationship?
<details>
<summary>click here for one possible answer</summary>
  
Composition is a relationship that persists.
</details>


### Practice Problems

Most classes in an object oriented program consist of some functionality and primitive types as well as some other embedded object types.   This practice problem will give you experience creating such a class using a nonesensical context.    Create a class called `Frankenstein` that includes a `String`, a `double`, a `Song` (from the OO Concepts section) and a `Pet`.  You can use one of the examples from the wiki for the pet class.

Ensure that your `Frankenstein` class has methods that allow the programmer to interact with the aggregate classes without needing to know about those classes.  For example, the `Frankenstein` class might have a `setTheSong(String)` method that takes a string representation of a song, parses it, and creates a song object from it.    It would also have methods for getting the song.     

Create a method in the `Frankenstein` class that sets the `String` member variable to some nicely formatted combination of the `Song` and the `Pet` information.   Create another method in the `Frankenstein` class that sets the `double` member variable to be the average number of alphanumerics in the aggregate classes.

One possible solution to this practice problem can be found on your docker container at:
`/course/practiceProblems/ooDesign/frankensteinClass`