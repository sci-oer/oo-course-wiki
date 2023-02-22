---
title: Java Hello World
description: 
published: true
date: 2022-06-02T15:48:44.419Z
tags: 
editor: markdown
dateCreated: 2022-05-02T19:52:27.429Z
---

# Practice Activities for [Hello World in Java](/java/helloWorld)



### Self Study Questions
1. What is the method signature for the method that is required in order to run a Java program?
<details>
<summary>click here for one possible answer</summary>
  
`public static void main(String[] args)`

</details>

2. What does the keyword ```new``` cause to happen?
<details>
<summary>click here for one possible answer</summary>
  
It cause the constructor to execute which should initialize the instance variables for the instance.
</details>

3. What method call causes output to be printed to the screen or console?
<details>
<summary>click here for one possible answer</summary>
  
the println method of the System.out class
`System.out.println("thing to print here");`
</details>


### Practice Problem

Create a java class called Hello and a second class called Runner.  The Hello class should contain two instance variables, one String and one int. It should have one constructor: ``` public Hello(int intVal, String strVal) ```.  It should have two methods ``` public void printMessage() ``` and ``` public void printNum()```.   
The Runner class should contain only a main method and should create several different instances of the Hello class with different values and then print out the values.   Experiment with assigning the value of one variable to a different variable and then printing.

A solution to this practice problem can be found on the drive of your course docker container at ```practiceProblems/java/HelloWorld```