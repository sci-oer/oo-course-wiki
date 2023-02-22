---
title: Binary Files
description: 
published: 1
date: 2022-08-17T20:07:43.784Z
tags: 
editor: markdown
dateCreated: 2022-08-17T18:14:19.558Z
---

### Prerequisite Knowledge
- [Streams](/inputOutput/streams)
- [Text Files](/inputOutput/textFiles)

# Binary Files
A binary file contains data that is not formatted as text.  In order for your program to understand the binary data in a file, it must know what kind of data to expect.

As was the case for interacting with text files, Java also provides several different mechanisms for interacting with binary files.

There are *legacy* mechanisms for interacting with binary files that make use of classes such as `BufferedInputStream`,`BufferedOutputStream`,`FileInputStream`, and `FileOutputStream`. These classes are used in much the same way that the legacy classes are used for interacting with text files- by wrapping file objects or other streams.

```
FileInputStream inputStream = new FileInputStream(inputFile);
FileOutputStream outputStream = new FileOutputStream(outputFile);
 ```

The new java io package `java.nio` provides static methods in the [`Files`](http://localhost:8000/docs/api/java.base/java/nio/file/Files.html) class for writing and reading binary files.   

In particular the following methods are very useful:

-`Files.newInputStream()`
-`Files.newOutputStream()`
-`Files.readAllBytes()`
-`Files.write(Path, arrayOfBytes)`

For example, the following code snippet will copy the contents of one file to another file. The read and write methods will throw an `IOException` if there are errors so they must be enclosed in a `try/catch`
```
Path source = Paths.get(inputFile);
byte[] bytesFromTarget = Files.readAllBytes(source);
 
Path destination = Paths.get(outputFile);
Files.write(destination, bytesFromTarget);
```



#### Practice 

- [Self Study Exercises and Practice Problems](/practiceActivities/inputOutput/binaryFiles)  
