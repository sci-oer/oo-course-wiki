---
title: Creating objects using constructors
description: 
published: 1
date: 2022-05-04T15:25:01.409Z
tags: 
editor: markdown
dateCreated: 2022-05-03T16:17:34.930Z
---

# Practice Activities for [Object creation with constructors](/dataStructures/collections)



### Self Study Questions
1. What would the java code look like for a constructor named Car that takes the parameters a `String` called model and an `int` called year?
<details>
<summary>click here for one possible answer</summary>
public Car (String type, int year) {
  
}
</details>
  
2. What is the java code for calling the constructor `Die` to the object name `roll`?
<details>
<summary>click here for one possible answer</summary>

`Die roll = new Die();`
</details>
  
3. What is the keyword used to make one constructor invoke another?
<details>
<summary>click here for one possible answer</summary>
  
`this` 
</details>


### Practice Problems

Start with your solution to the Frankenstein problem posed in the [Practice Activities for Aggregation](/practiceActivities/ooDesign/aggregation) section.   Create the following constructors for the `Frankenstein` class.
- a default constructor that takes no parameters.  New `Song` and `Pet` objects should be instantiated to create the whole `Frankenstein` object
- a constructor that takes a `Song` object and uses it as the aggregate member object.  A new `Pet` object should be instantiated.
- a constructor that takes a `Pet` object and uses it as the aggregate member object. A new `Song` object should be instantiated.
- a constructor that takes both a 'Song' object and a `Pet` object.

Write these constructors so that there is no duplicate code.   You will need to use the `this()` method.

A solution to this practice problem can be found on your docker container at `/practiceProblems/ooDesign/frankensteinWithConstructors`