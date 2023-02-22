---
title: Stdin
description: 
published: 1
date: 2022-08-17T20:07:18.290Z
tags: 
editor: markdown
dateCreated: 2022-08-17T18:14:30.298Z
---

#### Prerequisite Knowledge
- [Introduction to I/O Streams](/inputOutput/streams)
- [Standard Output](/inputOutput/stdout)

# Keyboard input with Scanner

In order to use keyboard input in a Java program, the keyboard must be attached to a [stream](/inputOutput/streams) and the stream used to read the input.

Java simplifies this task for the programmer by including built in classes that provide all the capabilities needed.  

1. The first built-in class is a [static member](/ooConcepts/classMembers) of the `System` class called `in`.   It is used in a java program with `System.in` and, by default, it references the keyboard as its input device. It is the java equivalent of `stdin` in a C program. `System.in`  is of the type `java.io.InputStream`.


2. The second built-in class that simplifies getting keyboard input is the `Scanner` class. The [Scanner](http://localhost:8000/docs/api/java.base/java/util/Scanner.html) class is found in the `java.util` package and has methods for reading a stream line by line, word by word (space-delimited), and character by character in addition to many other useful methods. An instance of the Scanner class is created by passing it the stream that it will be reading. Scanner can be used to read `System.in` of course, but it can also be used to read Files and other streams.


> Dont' try to have more than one `System.in` scanner operating in a program. That violates the rule of having only one reference to any single stream.
{.is-info}

The code shown below results in a reference called *keyboardScanner* that reads the stream of characters from the keyboard.
```
import java.util.Scanner;

keyboardScanner = new Scanner(System.in);
```
One of the easiest ways to use a scanner is to get the input one line at a time.  We could prompt the user to type something and capture their typing as shown below.

```
String userAnswer;
System.out.println("What is your favourite colour?");
userAnswer = keyboardScanner.nextLine();
System.out.println("Your answer was " + userAnswer);
```
The nextLine method of the Scanner class returns all the text up to the next 'newline' character (`\n`) but does not include the newline character in the returned String.



#### Practice 
 - Tutorial: [Getting Keyboard Input](http://localhost:8888/lab/tree/tutorials/inputOutput/userInput.ipynb) 

- [Self Study Exercises and Practice Problems](/practiceActivities/inputOutput/stdin)  
  

