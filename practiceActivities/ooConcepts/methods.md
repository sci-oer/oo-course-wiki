---
title: Instance Methods
description: 
published: 1
date: 2022-03-02T15:13:39.387Z
tags: 
editor: markdown
dateCreated: 2022-02-08T15:17:21.921Z
---

# Practice Activities for [Instance Methods](/ooConcepts/methods)

### Self Study Questions
1. What are the parts of a heading or signature for an instance method declaration in Java?
<details>
<summary>click here for one possible answer</summary>
  
- visibility (public, private, protected)
- return type (a type or `void`)
- method name (follow the naming conventions)
- parameter list
  
</details>

2. If an instance method returns a value at the conclusion of the computation, what is the keyword that is used to facilitate that?
<details>
<summary>click here for one possible answer</summary>
  
`return`

 note that `void` methods may also use the return keyword but it is better to design a void method so that all paths lead to a return after the end of the method is reached rather than have multiple return statements.
</details>

3. Write the method declaration for a private method called divide that returns a float and takes a double and an integer as parameters.
<details>
<summary>click here for one possible answer</summary>
  
`private float calculate(double paramOne, int paramTwo)`

</details>

4. Give the code that would invoke a method called multiply using a reference variable called myCalculator.  The method takes a single parameter of type double.
<details>
<summary>click here for one possible answer</summary>
  
```
  someDoubleVariable = some value that is set in the code;
  myCalculator.multiply(someDoubleVariable);
  ```

</details>

### Practice Problem

This practice problem will be gradually enhanced as you progress through the concepts.

Create a Java class called Calculator that has four instance methods: *add, subtract, multiply, divide*.   Each of the methods should return a double and each method takes two parameters that are also doubles.   

The method should execute the arithmetic operation noted by the name of the method and return the result.

Test your calculator by creating an instance of it in a Runner.java class and using it for several calculations.



A solution to this practice problem can be found on the drive of your course container at /course/practiceProblems/ooConcepts/calcWithInstanceMethods.



#