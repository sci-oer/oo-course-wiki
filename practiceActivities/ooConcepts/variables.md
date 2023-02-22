---
title: Instance Variables
description: 
published: 1
date: 2022-03-01T19:13:12.474Z
tags: 
editor: markdown
dateCreated: 2022-02-08T15:17:41.409Z
---

# Instance Variables
# Practice Activities for [Instance Variables](/ooConcepts/variables)



### Self Study Questions
1. What is the Java declaration for an instance variable of type String?
<details>
<summary>click here for one possible answer</summary>
  
`private String variableName;`

</details>

2. If two instances of a class containing a `name` instance variable are created, and one instance is set to have a name of `Jordan`, what will the name variable of the second instance be set to?
<details>
<summary>click here for one possible answer</summary>
The second instance is unchanged when the state of the first instance is changed.
</details>

3. Suppose a programmer created a class representing a Pet and another class representing an Owner.  Is it possible for the Owner class to contain an instance variable of type Pet? 
<details>
<summary>click here for one possible answer</summary>
  
Yes, instance variables can be of any type. For example:
```
  public class Owner {
      private String ownerName;
      private Pet myPet;
  
     public nameMyPet(String name){
  /*owner class uses the pet instance variable to set the pets name 
   by calling methods that belong to the pet class */
  			myPet.setName(name);
  }
```
</details>

### Practice Problem

This practice problem builds on the one presented as [practice problem for Instance Methods](/practiceActivities/ooConcepts/methods).  If you have not completed that activity, please do so.

The calculator can be made more useful by adding variables to hold values between method invocations.   In this way the calculator's methods can operate on the value stored in an instance variable and multiple calculators could have separate values.

Modify the calculator class so that it has a double as an instance variable.  It should store the results of every calculation in that variable and provide a mechanism for retrieving the value (an accessor method).  This instance variable should not have a mutator method.

Adjust the instance methods so that they no longer take two parameters.  Instead they simply perform the calculation with the value currently held by the calculator.

Test your revised calculator thoroughly in the Runner class.

*A solution to this practice problem can be found on the drive of your course container at /course/practiceProblems/ooConcepts/calcWithInstanceVariables.* 