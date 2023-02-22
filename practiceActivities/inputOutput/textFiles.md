---
title: Text Files
description: 
published: 1
date: 2022-03-04T21:39:10.860Z
tags: 
editor: markdown
dateCreated: 2022-02-08T15:16:33.474Z
---

# Text Files
# Practice Activities for [Using Text Files](/inputOutput/textFiles)



### Self Study Questions
1. What built in Java classes are useful when reading or writing with text files?
<details>
<summary>click here for one possible answer</summary>
There are many useful classes including:
 - `BufferedReader`
 - `BufferedWriter`
 - `FileWriter`
 - `java.nio.file.Files`
 - `java.nio.file.Paths`
 - `java.nio.file.FileSystems`
 It is worth exploring the options and choosing one to learn well.
</details>

2. Explain the difference between an absolute path and a relative path.
<details>
<summary>click here for one possible answer</summary>
  
An absolute path starts at the root of the file system and begins with a forward slash.  A relative path starts at the current directory and does not begin with a slash.  *Note* if you are experimenting with paths on a Windows system you will have to use backslashes instead of forward slashes.
</details>

3. What type of exception must be caught when executing methods that interact with files?
<details>
<summary>click here for one possible answer</summary>
  
`IOException`. You must also import java.io.IOException.

</details>


### Practice Problems
1. Create a Java class called FileRead that provides at least one method for for reading in a text file.  Your java class should have a constructor that takes two parameters and instance variables to store the value of those parameters.   The beginning of the class is shown below.
```
public class FileRead {
   private String fileName;
   private String location;

 
 public FileRead(String targetFile, String targetPath){
    fileName = targetFile;
    location = targetPath;
 }
```
Create a second class called Runner.java that contains a main method.  In that main method demonstrate the use of your FileRead class.   

A solution to this practice problem can be found at `/course/practiceProblems/inputOutput/textFileRead`.  This solution demonstrates three possible methods of reading a text file.

2. Create a Java class called FileWrite that provides at least one method for writing to a text file.  The FileWrite class should have a similar constructor as the FileRead class. Create a second class called Runner.java that contains a main method.  In that main method demonstrate the use of your FileWrite class. 

A solution to this practice problem can be found at `/course/practiceProblems/inputOutput/textFileWrite`.  This solution demonstrates three possible methods of writing to a text file.
