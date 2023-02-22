---
title: Binary Files
description: 
published: true
date: 2022-05-20T16:10:01.965Z
tags: 
editor: markdown
dateCreated: 2022-05-02T19:52:08.538Z
---

# Practice Activities for [Binary Files](/inputOutput/binaryFiles)



### Self Study Questions
It is worth your time to learn more about the [`java.nio.Files`](http://localhost:8000/api/java.base/java/nio/file/Files.html) class.  These questions are all about that class.

1. What are the parameters to the `Files.newOutputStream()` method?
<details>
<summary>click here for one possible answer</summary>
  
Files.newOutputStream() takes a `Path` and `OpenOptions` as parameters.  The OpenOptions parameter is optional.
</details>

2. What is the return type for Files.newInputStream()?  What package is that type found in?
<details>
<summary>click here for one possible answer</summary>
  
The return type is `InputStream`.  It is found in the `java.io` package.
</details>

3. Can the Files.write() method be used to write to a binary file?
<details>
<summary>click here for one possible answer</summary>
  
Yes, the write() method has been overloaded to allow for a variety of parameter combinations.  One of those combinations includes an array of type `byte` that can be used to write to a binary file.
</details>


### Practice Problem

Image files are one example of binary files that are used regularly.  Write a java program that will inspect all of the files in a folder and move any that are png images to a new folder that the program creates.    Have your program prompt the user for the folder to inspect as well as the folder to move the png images to.   You can use the `java.nio.Files` class to accomplish most of these tasks.

A solution to this practice problem can be found on the file system of the docker container at: `/course/practiceProblems/inputOutput/binaryFiles`