---
title: Polymorphism via Inheritance
description: 
published: 1
date: 2022-05-04T17:07:24.877Z
tags: 
editor: markdown
dateCreated: 2022-04-08T16:52:04.574Z
---

# Polymorphism via Inheritance

# Practice Activities for [Polymorphism via Inheritance](/ooDesign/inheritance)



### Self Study Questions
1. Since the instance and class variables should be private, how does the subclass accesses those variables?
<details>
<summary>click here for one possible answer</summary>
  
getters and setters.
</details>

2. What relationship should a subclass share with its super class?
<details>
<summary>click here for one possible answer</summary>
  
an "is a" or "is a kind of" relationship.
</details>

3. What is the Java code for a subclass called car with a super class called vehicle?
<details>
<summary>click here for one possible answer</summary>
  
public class car extends vehicle {
  
}
</details>

4. What is the tag that lets the Java compiler know that we intend the subclass method to override the base class method?
<details>
<summary>click here for one possible answer</summary>
  
**@Override**
</details>

5. If the abstract methods are defined with a header, but no implementation is given, what must the subclass do?
<details>
<summary>click here for one possible answer</summary>
  
A subclass must implement all of the abstract methods.
</details>

### Practice Problem

Start with the solution to the problem posed in [Practice Activities for Constructors](/practiceActivities/ooDesign/constructors).

Create a subclass of `Frankenstein` called `Meatloaf`.  Add an instance variable to `Rocky` that is of type `Die` (you can get one implementation of `Die` from [Instance Variables](/ooConcepts/variables)).  Set the number of sides on the die to the average number of characters value from `Frankenstein`.  Add a method to `Rocky` that rolls the die and outputs the value.

You should not have to modify the `Frankenstein` class at all to do this.  If you do find yourself modifying it, make note of what you modify and consider whether that shoud have been part of the original design of the class.

One solution to this practice problem can be found at `/course/practiceProblems/ooDesign/childOfFrankenstein`
