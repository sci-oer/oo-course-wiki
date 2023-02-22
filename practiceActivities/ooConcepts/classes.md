---
title: Practice for Classes, Instances and Objects
description: 
published: true
date: 2022-06-02T15:59:53.539Z
tags: 
editor: markdown
dateCreated: 2022-05-02T19:52:41.488Z
---

# Practice Activities for [Classes, Instances and Objects](/ooConcepts/classes)
### Self Study Questions
1. Write the line of code that declares a variable of type String.  Write a second line of code that assigns the value "OO is fun" to that variable.
<details>
<summary>click here for one possible answer</summary>
  
`String someVariableName;`
`someVariableName = "OO is fun";`
</details>

2. Suppose you have created a class called Book. Write the line of code that will declare a variable of type Book, create an object of that type using the default constructor, and assign that object to the variable you have created.
<details>
<summary>click here for one possible answer</summary>
 
`Book aNewBook = new Book();`
</details>

3. Further suppose that the Book class has two methods: setAuthor() and setTitle(), and that both methods take a single parameter of type String.  Write two lines of code that set the author name to "Daisy Duck" and the title of the book to "Quackers".
<details>
<summary>click here for one possible answer</summary>
 
`aNewBook.setAuthor("Daisy Duck");`
 `aNewBook.setTitle("Quackers");`
</details>


### Practice Problems

Solutions to these practice problems can be found on the drive of your course container at ```/course/practicProblems/ooConcepts```.  The solutions include proper project structure and a gradle build file.  

1. Create a Java class that represents information about a song in a tune library.  The information should include the name of the artist, the title of the song, the year the song was released, and a quality rating for the song that is a number between 0 and 5. Provide methods to set all of the attributes and methods to get the current value of all attributes.   Provide an additional method that returns a nicely formatted ```String``` representation of the song for printing.  Do not print in the Song class.
Create a second class called Runner.java that can be used to create instances of your song class and exercise the capabilities of the class.  The solution for this problem is found in the ```classDefinition-Song``` subfolder.