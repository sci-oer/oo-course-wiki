---
title: Using References
description: 
published: 1
date: 2022-02-25T21:27:57.212Z
tags: 
editor: markdown
dateCreated: 2022-02-08T15:17:36.575Z
---

# Memory and References
# Practice Activities for [Memory and References](/ooConcepts/references)



### Self Study Questions
1. What java reserved word causes memory to be allocated for an object?
<details>
<summary>click here for one possible answer</summary>
  
`new`

</details>

2. Java doesn't require the programmer to directly manipulate memory but it does use pointers.  What are pointers called in a Java program?
<details>
<summary>click here for one possible answer</summary>
  
references
</details>

3. What happens to the memory allocated to an instance if all of the references that were pointing to it are changed to point to different instances?
<details>
<summary>click here for one possible answer</summary>
  
the memory is marked for garbage collection
</details>

4. What is the java code for declaring a reference variable of type Calendar?
<details>
<summary>click here for one possible answer</summary>
  
`Calendar referenceVariableName;`
</details>

4. What is the result from running this code snippet?  Assume the Dog class is complete.
```
Dog fido;
fido = new Dog();
fido.setName("fido");
fido.setName("bowser");
fido = new Dog();
```
<details>
<summary>click here for one possible answer</summary>
The reference variable fido is created and then set to point at a new instance.  The name variable for that instance is set to fido.  In the next line of code it is set to bowser. The next line of code allocates memory for a second instance of type Dog and points the fido reference variable at this newly allocated instance.   The memory for the first instance has no more references associated with it and it is marked for garbage collection.

</details>