---
title: Text Files
description: 
published: 1
date: 2022-08-17T19:18:55.401Z
tags: 
editor: markdown
dateCreated: 2022-08-17T18:14:38.583Z
---

### Prerequisite Knowledge
- [Streams](/inputOutput/streams)

# Text Files

A text file can be attached to a stream and used for either input or output. In order to use any sort of file successfully, the programmer must first understand the hierarchical nature of file systems and file paths.

### Files and Paths
The file system on a modern computer uses a hierarchical file/folder structure that helps keep files organized for human understanding.   The resulting structure looks like a tree when depicted graphically.  
![screenshot of the file folder represention of the course subfolder](/images/fileHierarchy.png)

In the image above you see the file/folder structure for the *course* subdirectory of this docker container. 
There is a file called *build.gradle* circled in blue.  The filename for that file is `build.gradle`.   The **path** to that file is `/course/practiceProblems/ooConcepts/calcWithClassMembers/`.  If one wanted to open that file with a program, the path should be concatentated to the filename to produce `/course/practiceProblems/ooConcepts/calcWithClassMembers/build.gradle`

One more important concept with respect to paths is the notion of the file system **root**. The file system has a root folder that is a the "top" of the tree conceptually. On the command line you can get to that root folder by typing `cd /`. The root folder of the docker container contains the following files and folders: 
```
bin     entrypoint.sh  jupyter.sh  libx32    opt   sbin  usr
boot    etc            lib         media     proc  srv   var
course  home           lib32       mnt       root  sys   wiki.sh
dev     jupyter        lib64       motd.txt  run   tmp   wiki_data
```
The *absolute path* for any file in a system starts at that root represented by a forward slash `/`.   So `/course/practiceProblems/ooConcepts/calcWithClassMembers/build.gradle` indicates that one should start at the root of the file system and navigate folders as given by the path.

If a file path does *not* start with a forward slash, that means that the path is **relative** to the current location.   In the case of relative paths, it is crucial to know what the current directory is as well as the relative path to the desired file. 

For example, the path to the build.gradle file from the previous example would be `ooConcepts/calcWithClassMembers/build.gradle` if the current directory were *practiceProblems* but the path to the same file would be `calcWithClassMembers/build.gradle` if the current directory were *ooConcepts*.

Relative paths are usually more useful because not every file system is the same so a fully specified path may be correct on one system but incorrect on another.

### Locating and Opening Files


A programmer can combine strings to produce the path to a file and use that string to open the file object.   This is accomplished using the `FileReader` class from `java.io` and wrapping a `BufferedReader` around that class.

```
    myReader = new BufferedReader(new FileReader(pathToFile));
```
This mechanism has been used for a long time, but the past few versions of Java offer a more robust approach that first creates an instance of type `Path` that is installation independent and then using that instance to open the file.
```
Path path = FileSystems.getDefault().getPath(path, fileName);
BufferedReader myReader = Files.newBufferedReader(path)
```
Note that `FileSystems` and `Files` are classes that contain only static methods intended to help with using the other classes.  These more modern file reading classes are in the `java.nio.file` package.  These classes must be imported before they can be used.


## Getting input from a file
 Use **BufferedReader** for line-at-a-time reading.
  1. Open a file.
  1. Read from the file.
  1. Close the file.
  
The BufferedReader will return null if it reaches the end of the file so a null-controlled loop can be used to read the entire file.

```
     Path path = FileSystems.getDefault().getPath(location, fileName);
    try {
      BufferedReader myReader = Files.newBufferedReader(path);
      String oneLine = myReader.readLine();
      System.out.println(oneLine);
      myReader.close();
    } catch (Exception e) {
      // do something to handle the exception here
    }
```


If the file being read is relatively small, the `Files` class provides a static method that will handle opening and closing the file without programmer intervention.  The lines of the file are returned as a `List<String>`.

```
List<String> lines;
Path path = FileSystems.getDefault().getPath(location, fileName);
try{
    lines = Files.readAllLines(path);
   }catch(IOException e){
       //do something to handle exception
   }
```
 
## Writing output to a file
Use **FileWriter** for text files.
   1. Open a file
   1. Write to the file
   1. Close the file
   
You must use [try/catch](/errors/exceptions) because failure at any point results in an **IOException**.

The [FileWriter](http://localhost:8000/docs/api/java.base/java/io/FileWriter.html) class provides a `write(String)` method.  You will need to explicitly add newline characters where you want line breaks in the file.

```
try {
    FileWriter writer = new FileWriter("name of file");
    while(there is more text to write) {
        ...
        writer.write(next piece of text);
        ...
    }
}catch(IOException e) {
    something went wrong with accessing the file
}
```

The `Files` class from the `java.nio.files` package provides two additional mechanisms for writing text to a file.   The first is to use the `newBufferedWriter()` method to obtain a BufferedWriter given an instance of `Path`.

```
BufferedWriter fileWriter = Files.newBufferedWriter(path);
```
Once a BufferedWriter object exists, the `write()` method can be used to push text to the file.

The second mechanism that the `Files` class provides is a set of static methods that will write to a file give a path and information to write.   There are several variations of this method. One that takes a string and an optional *open option* is shown below.

```
 Path path = FileSystems.getDefault().getPath(location, fileName);
 try {
   Files.writeString(path,"this is what I want in the file");
   Files.writeString(path,"and another thing", StandardOpenOption.APPEND);
} catch(IOException e) {
       //do something to handle exception
   }
```
Java provides many mechanisms for interacting with files.  The choice of which to use depends on the programming style and requirements of the project and the personal preferences of the programmer.

#### Recorded Lecture
[Reading and Writing Text files](http://localhost:8000/lectures/inputOutput/TextFiles/)

#### Practice 
 - Tutorial: [Reading Text Files](http://localhost:8888/lab/tree/tutorials/inputOutput/bufferedReader.ipynb) 
 - Tutorial: [Writing Text Files](http://localhost:8888/lab/tree/tutorials/inputOutput/bufferedWriter.ipynb) 


- [Self Study Exercises and Practice Problems](/practiceActivities/inputOutput/textFiles)  