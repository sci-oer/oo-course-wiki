---
title: Object Serialization
description: 
published: 1
date: 2022-08-17T19:20:06.022Z
tags: 
editor: markdown
dateCreated: 2022-08-17T18:14:27.585Z
---

# Object Serialization
Sometimes it is necessary to persistently save the state of an object.   Perhaps the program needs to stop computation for a while and then pick up again later, or perhaps the program needs to send the object and its state to some other program. There are many different solutions to this problem, one of which is object serialization.

We use the term **serialize** to describe creating a stream of binary data from some portion of a program.   It is serial because the order of the data cannot be changed without destroying the readability of the data.  Serialized data can be stored and then read later to restore the elements of the program to the state they were in when serialized.

Java allows the use of serialization to convert an object to a stream of bytes that can be persistently saved.  That saved stream can be used to load the object back into the program and restore all of the values that were present when it was serialized.  One use case for object serialization in Java is to save the state of a Java program, such as a game, in a file that can be used later to reload the program to the state it was at when it was shut down.


### What is the state of an object
The **State**  of an object is the the values assigned to the instance variables for that objecct.  

We can save the *state* of  an object before closing a program by writing those objects to a stream.  The stream can be used to create a file.  (The stream could also be used in other ways, such as to push the objects to a database)
 
To reloading the state, open and read the file and use the contents to reconstruct the objects.   Java serialization handles the conversion from object to stream and back to object for you. 

#### Java Serialization

* Serialization is accomplished through implemeting an interface.
* The class(es) you want to serialize must implement the `Serializable` interface (found in **java.io.Serializable**)
- Recommended to add a private variable to your serializable class
  - `Private  final long serialVersionUID= value here;`
  - Java will create an id for you using serialver
  - This variable helps Java ensure that the object being loaded matches the current version of the class,
* Serializing a composite object also saves all of the aggregates
    * if a Game class has instance variables for Player, Rooms, and Items those will all be serialized when Game is serialized.
    * the aggregates must also implement `Serializable`
*  Serialization saves an object's state.  Class variables are ignored.
    * Static variables are class variables
    * If you have static variables that must be serialized that must be handled separately
    * for example, you could create an instance of a special purpose class that saves the static values as serial data.
- If an instance variable is marked transient it will not be serialized

The code shown below is an example of a class that implements the Serializable interface.  It has a single method for printing out values, simply to demonstrate the effects of serialization.   

```
public class SerializationDemo implements java.io.Serializable {

  /**
   * your IDE will generate this if you want, or use serialver on the command line.
   */
  private static final long serialVersionUID = -3788086098781612036L;
  private int myIntegerValue;
  private String myName;

  /**
   * Default constructor.
   * @param inputInt integer value
   * @param inputName String name
   */
  public SerializationDemo(int inputInt, String inputName) {
    myIntegerValue = inputInt;
    myName = inputName;
  }
  /**
   * Print Method to output name and value.
   */
  public void printMe() {
    System.out.print("Name: " + myName);
    System.out.println(" Val: " + myIntegerValue);
  }
}
```
The code below is what must be executed in order to save a Serializable object to a file.   

```
    //Any filename extension is ok. Extensions are arbitrary
    String filename = "aNameIMadeUp.someEnding";

/* creating the object to be serialized.  Normally this
would happen as part of the operation of the software, not
immediately before serialization*/

    SerializationDemo object = new SerializationDemo(
      42,
      "This is a test of serialization"
    );
    object.printMe();  //just shows the values as input

/*Serialization starts here */

    try {  //as with most IO you must catch exceptions
      
      FileOutputStream outPutStream = new FileOutputStream(filename);
      ObjectOutputStream outPutDest = new ObjectOutputStream(outPutStream);

      // Method for serialization of object
      outPutDest.writeObject(object);

      outPutDest.close();
      outPutStream.close();

      System.out.println("Object has been serialized");
    } catch (IOException ex) {
      System.out.println(ex);
    }
```
Once the object(s) are serialized there will be a file on the file system that is named as indicated in the code.   A different method can be run any time in the future to load that saved object.

In the example below, notice that we must **cast** the object read to the correct type (line 12).

```
  public static void main(String[] args) {
    String filename = "aNameIMadeUp.someEnding";
    SerializationDemo gotItBack = null;

    // Deserialization
    try (
      ObjectInputStream in = new ObjectInputStream(
        new FileInputStream(filename)
      );
    ) {
      // Method for deserialization of object
      gotItBack = (SerializationDemo) in.readObject();

      System.out.println("Object has been deserialized ");
      gotItBack.printMe();
    } catch (IOException ex) {
      System.out.println("IOException is caught " + ex);
    } catch (ClassNotFoundException ex) {
      System.out.println("ClassNotFoundException is caught " + ex);
    }
  }
}
```

Object serialization is a useful technique in situations where the object in question will be stored persistently to be read in at a later time on program restart (e.g. save files).  

It can also be used to send serialized objects across network connections to remote programs.  That application  of serialization can be difficult to debug.



