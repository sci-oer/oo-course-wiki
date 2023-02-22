---
title: Main method
description: 
published: 1
date: 2022-02-23T21:18:45.974Z
tags: 
editor: markdown
dateCreated: 2022-02-08T15:16:53.405Z
---

# Practice Activities for [Java's Main Method](/java/mainMethod)



### Self Study Questions
1. What is the syntax for declaring a main method in Java?
<details>
<summary>click here for one possible answer</summary>
  
`public static void main(String[] args){}`

</details>

2. What would you type to run the main method of a Java program called RunMe?  Assume the class file is in your working directory.
<details>
<summary>click here for one possible answer</summary>
  
`java RunMe`

</details>

3. How does the main method in a Java program access command line parameters that it is sent?
<details>
<summary>click here for one possible answer</summary>
  
The command line parameters are contained in the String array called `args` that is the single parameter to the main method. The parameters can be accessed by examining the elements of the array, beginning at position 0.
</details>


### Practice Problem

Create a class called Demo that contains three public methods: messageOne(), messageTwo(), and messageThree().   Each method should print a single line of text.  Create a second class called Runner that has a main method.   In that main method create an instance of your Demo class and use all of the methods.

> A solution to this practice problem can be found on the drive of your course docker container at `practiceProblems/java/DemoMain`
{.is-info}
