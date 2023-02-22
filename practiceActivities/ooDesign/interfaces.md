---
title: Polymorphism via Interfaces
description: 
published: 1
date: 2022-05-04T18:41:22.965Z
tags: 
editor: markdown
dateCreated: 2022-04-08T16:52:08.596Z
---

# Practice Activities for [Polymorphism via Interfaces](/ooDesign/interfaces)



### Self Study Questions
1. What is the Java code for defining a class named "circles" implementing an interface called "shapes"
<details>
<summary>click here for one possible answer</summary>
  
`public class circles implements shapes { }`
</details>

2. For "comes before", what are the the three rules of total ordering that must be satisfied?
<details>
<summary>click here for one possible answer</summary>
  
**Irreflexivity, Trichotomy, and Transitivity.**
</details>

3. Can interfaces contain instance variables or any complete method definitions?
<details>
<summary>click here for one possible answer</summary>
  
No. Interfaces must contain method headings and constant definitions only.
</details>


### Practice Problems

Modify the solution for the problem stated in [Practice Activities for Constructors](/practiceActivities/ooDesign/constructors) so that the `Frankenstein` class implements the [`Comparable` interface](http://localhost:8000/docs/api/java.base/java/lang/Comparable.html).   Use the `Runner` class to demonstrate how two objects can be compared.   Create an `ArrayList` of `Frankenstein` objects and show how the sort method works.

A solution to this problem can be found on your docker container at `/course/practiceProblems/ooDesign/comparingFrankenstein`