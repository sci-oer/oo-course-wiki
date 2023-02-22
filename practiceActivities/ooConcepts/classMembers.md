---
title: Class Methods and Variables
description: 
published: 1
date: 2022-03-02T19:12:56.813Z
tags: 
editor: markdown
dateCreated: 2022-02-08T15:17:02.312Z
---

# Practice Activities for [Class Members](/ooConcepts/classMembers)

### Self Study Questions
1. What should the visibility of a class variable be?
<details>
<summary>click here for one possible answer</summary>
  
`private`

</details>

2. Can a static variable be read or modified in an instance method?
<details>
<summary>click here for one possible answer</summary>
  
Yes, static variables can be used in an static, or class,  method but also can be used in an instance method.
</details>

3. I created a static variable in my class so that I could use it in a static method but now when I change the value in one object it changes it in all of them! How do I fix it?
<details>
<summary>click here for one possible answer</summary>
  Every object, or instance, of a class shares the same memory space for each static variable.   Don't use static variables to represent state for individual instances.   Change the variable to be an instance variable and instantiate an object in the static method to use the accessor and mutator methods for it.
</details>


### Practice Problem

This practice problem builds on the one presented as [practice problem for Instance Variables](/practiceActivities/ooConcepts/variables).  If you have not completed that activity, please do so.

Add a constant to your calculator that represents the mathematical value of PI.   

Add two static methods to the Calculator, one that compares two doubles and returns the largest of the two numbers.  The second static method should return the square of the parameter value(a double).

Finally, add a class variable to your calculator that is a shared variable that allows calculators to share a value with other calculators.   Call this class variable `register`.   

Write an instance method called addToRegister() that takes a double as a parameter and adds that value to the register and returns the new value.    Write a second instance method that resets the register to zero.

Test your revised calculator thoroughly in the Runner class.  In particular make sure you experiment with using the register class variable to share data between instances of the Calculator.

*A solution to this practice problem can be found on the drive of your course container at /course/practiceProblems/ooConcepts/calcWithClassMembers.* 