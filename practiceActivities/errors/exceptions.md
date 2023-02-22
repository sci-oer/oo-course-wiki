---
title: Exceptions
description: 
published: true
date: 2022-06-02T16:37:58.933Z
tags: 
editor: markdown
dateCreated: 2022-05-02T19:51:22.349Z
---

# Practice Activities for [Exceptions](/errors/exceptions)



### Self Study Questions
1. What is the key distinction between a *Checked Exception* and an *Unchecked Exception* in Java?
<details>
<summary>click here for one possible answer</summary>
  
A checked exception must be caught in a try/catch or rethrown by the method.  Unchecked exceptions do not have to be caught or thrown.
  
</details>

2. What is the purpose of "try with resources"?
<details>
<summary>click here for one possible answer</summary>
  
The "try with resources" syntax ensures that a closeable resource is always closed after the block executes, whether or not an exception occured.  It functions like a finally clause.
  
</details>

3. What is the most effective way to write a try/catch block to handle multiple exceptions?
<details>
<summary>click here for one possible answer</summary>
  
Create a separate catch block for each type of exception and ensure that those separate blocks are ordered from most specific to most general.
  
</details>


### Practice Problem

Enhance your most advanced solution to the Calculator practice problem by adding exceptions to handle errors.   Add an exception to the divide method to ensure that divide by zero doesn't happen and allows the calculator operator to try again.   Add another exception that is triggered if the storedValue of the calculator is in danger of exceeding the capacity of the variable type.

Change the Runner.java code so that it prompts the user for input to the calculator and allows the user to recover if an exception is thrown.

A solution to this practice problem can be found at
`/course/practiceProblems/errors/calcWithExceptions`