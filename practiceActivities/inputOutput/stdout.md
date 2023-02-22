---
title: Stdout
description: 
published: 1
date: 2022-03-04T15:53:59.532Z
tags: 
editor: markdown
dateCreated: 2022-02-08T15:16:18.831Z
---

# Practice Activities for [Providing Output](/inputOutput/stdout)


### Self Study Questions
1. What static member of `System` is used to provide terminal output to users?
<details>
<summary>click here for one possible answer</summary>
  
`System.out`
 One of the methods often used is `println()`

</details>

2. List three options for concatenating strings in Java.
<details>
<summary>click here for one possible answer</summary>
  
- use the `+` operator
- use the String `concat()` method
- use the StringBuilder `append()` method
</details>

3. Why is there no required import statement to use the StringBuilder class?
<details>
<summary>click here for one possible answer</summary>
  
The StringBuilder class is in the `java.lang` package and the classes in that package are automatically imported.
  
</details>


### Practice Problem
Write a *MadLibs* Java program that uses the StringBuilder class to insert a set of words into a   a simple nursery rhyme  substituting for other key words in the rhyme.   For example:  Suppose that the set of words was `Betty`, `car`, `book`, `red` and `cucumber`.   If we had written the *MadLib* program to use the rhyme **Mary had a little lamb. Its fleece was white as snow.** the program would output `Betty had a little car. Its book was red as cucumber.`
Use any simple rhyme or poem you like.

A solution to this practice problem can be found on the drive of your course docker container at `/course/practicProblems/inputOutput/madLibsFormat`