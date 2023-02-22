---
title: Practice Activities for Serialization
description: 
published: 1
date: 2022-05-04T18:30:10.124Z
tags: 
editor: markdown
dateCreated: 2022-05-04T18:05:24.112Z
---

# Practice Activities for [Serialization](/inputOutput/serialization)



### Self Study Questions
1. What is the term used to describe creating a stream of binary data from some portion of a program?
<details>
<summary>click here for one possible answer</summary>
  
**Serialize**.
</details>

2. Classes you want to serialize must implement which interface, and where is it found?
<details>
<summary>click here for one possible answer</summary>
  
`Serializable` (found in **java.io.Serializable**).
</details>

3. Write the Java code for a class named "Serialization Practice" that implements the Serializable interface.
<details>
<summary>click here for one possible answer</summary>
  
`public class SerializationPractice implements java.io.Serializable {`

`}`
</details>


### Practice Problem

Modify the solution for the practice problem found at [Practice Activities for Constructors](/practiceActivities/ooDesign/constructors) to make the `Frankenstein` class serializable.    Using the `Runner` class demonstrate that different instances can be correctly saved persistently to file and reloaded.

One possible solution to this practice problem can be found on your docker container at:
`/course/practiceProblems/inputOutput/savingFrankenstein`