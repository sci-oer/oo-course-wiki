---
title: Streams
description: 
published: true
date: 2022-09-07T18:22:24.540Z
tags: 
editor: markdown
dateCreated: 2022-05-02T19:47:25.363Z
---


# Input and output in OO programming

Unless a computer program is strictly computing a value for some constant, it will eventually need input to its operations and it will need to provide output.  Sometimes the input/output is an interaction with humans,  sometimes it is an interaction with another program (e.g. a web service), sometimes it is an interaction with a file system. It could also be interactions with other types of devices such as sensors.

This type of interation is grouped together and called **I/O** which is a short way of indicating **Input/Output**

> - I/O provides input to the program
> - I/O allows the program to provide output which is sometimes input for other programs or devices
> - I/O in an OO program is done by passing messages to objects
{.is-info}

## I/O Streams

A stream is a connection to a source of data or to a destination for data (sometimes both). I/O is stream-based for modern computing languages.

Think of the stream as a continous sequence of data that can be observed (read) when desired.  One image that is often used is that of a water hose and a stream of water.   Something pushes the water into the hose and water comes out the other end.  A stream of data is similar in that data is "pushed" into the stream by some input device and then read by some other device or program that is observing (reading) the stream.

![input streams such as buffered reader shown taking input from devices such as microphones and mice.  output streams such as buffered writer shown sending output to devices such as printers and terminals.](/images/streams.png)
#### Stream Types
- An input stream may be associated with devices used to communicate such as keyboard, mouse, stylus, trackpad.
- A file can be either an input stream or an output stream.  The display of a computer is an output stream.
- Different streams have different characteristics. For example:
   - A file has a definite length, and therefore an end.
   - Keyboard input has no specific end.
   - Some streams are binary data.
   - Some streams are text.
   
> **We can use a stream to:**
>     1. get data (input stream)  a hose siphoning water out of a bucket
>     2. push data (output stream)  a hose filling a bucket
{.is-info}

## Using Java Streams for I/O

When you open a stream, you are making a connection to some device or location that is external to the program.  
Once the connection is made, the program doesn't need to know anything about the external device because it just uses the stream. 

Think back to the hose example. Once you turn the water on, you don’t really worry about where the water is coming from.

> The process for using streams for I/O in Java is the same regardless of which type of stream you are using:
> 1. Open the stream
> 1. Do the input/output operation
> 1. Close the stream
{.is-info}


Streams are  often **wrapped** to combine the features of several streams.  In this context, wrapping means that we send one stream to the constructor of a second stream to an object with multiple sets of capabilities.

For example, suppose we wanted to read the contents of a text file.   The `FileReader` class has the capability to read a file, but is limited to reading one character at a time.  If we wrap the `FileReader` object in a `BufferedReader` object we can combine the capabilities of both to have a reader giving us an input stream with more capabilities.

```
import java.io.BufferedReader;
import java.io.FileReader;

String filename = "test.txt";
FileReader fileRead = new FileReader(filename);
//wrapping the FileReader in a BufferedReader
BufferedReader myReader = new BufferedReader(fileRead);
```

Note that the code sample above will not compile because we have not handled the **exceptions** that can be thrown by instantiating a FileReader object. [Exceptions ](/errors/exceptions) are Java's mechanism for handling errors and unexpected events in execution.   Because I/O is error prone (e.g. the file doesn't exist), we have to take precautions that the errors don't crash our program and exceptions are used to communicate those errors.
 
#### Closing Streams
A stream is an expensive resource computationally. There is a limit on the number of streams that you can have open at one time. You should never have more than one stream open on the same resource. You must close a stream before you can open with a different reference.  Java will normally close your streams for you when your program ends but that is not considered good practice.

> Always close your streams!
{.is-success}

    
#### Reader and Writer classes
Readers and Writers deal with textual input.  The classes are designed to work with char type data.  There are many subclasses of Readers and Writers. The most common ones you will likely use include:
  - [java.io.BufferedReader](http://localhost:8000/docs/api/java.base/java/io/BufferedReader.html)
  - [java.io.InputStreamReader](http://localhost:8000/docs/api/java.base/java/io/InputStreamReader.html)
  - [java.io.BufferedWriter](http://localhost:8000/docs/api/java.base/java/io/BufferedWriter.html)
  - [java.io.OutputStreamWriter](http://localhost:8000/docs/api/java.base/java/io/OutputStreamWriter.html)

#### DataInput and DataOutput classes
Input and Output stream classes are designed to work with binary data.  Again, there are many possible classes in the `java.io` package.  Some that you will likely use include:

- [java.io.DataOutputStream](http://localhost:8000/docs/api/java.base/java/io/DataOutputStream.html)
- [java.io.DataInputStream](http://localhost:8000/docs/api/java.base/java/io/DataInputStream.html)
- [java.io.ObjectOutputStream](http://localhost:8000/docs/api/java.base/java/io/ObjectOutputStream.html)
- [java.io.ObjectInputStream](http://localhost:8000/docs/api/java.base/java/io/ObjectInputStream.html)




  

