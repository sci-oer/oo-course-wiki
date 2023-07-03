---
title: Main method
description: 
published: true
date: 2022-08-29T20:10:22.813Z
tags: 
editor: markdown
dateCreated: 2022-05-02T19:47:49.648Z
---


# Java's default method: main()



The creators of the Java programming language chose to specify a single method name as the one that would be executed when a program is run. The name of that method is `main`.   

The main method must be defined according to specific rules.

1. It must be a static method.  This means that it cannot be invoked from an instance of a class.  Rather it is invoked as a class method that cannot use instance data.
1. It must take an array of type `String` as a parameter.  This array contains the command line parameters given to the program in the same way that `argv` contains them for a C program.
1. It must be a public method with a void return type.
1. It must be called `main`.  You will get unexpected results if you call it `Main`.

`public static void main(String[] args)`


### Executing the main method

Integrated development environments and build tools hide much of the inner workings of how programs are run. It is worth understanding how do run a java program without any of those tools.

To run a java program you must have the interpreter installed and you must know where the byte-code files are on the disk of the computer.  The java interpreter automatically executes the main method for the class it is asked to run.

Lets suppose that we had constructed a program to keep track of pets boarding at an animal care facility. In this imaginary program we have a class for Pets, a class for the Facility, and a class for Staff. We also have a class called Runner that is where the `main` method is defined.

Once we have compiled those classes there will be four files called Pets.class, Facility.class, Staff.class and Runner.class. For now lets assume those files are in our curren working directory.

To run this program we would type `java Runner`. That tells the Java Virtual Machine to execute the main method in the Runner class.

**More than one `main`**
It is permissible to have a main method in more than one class. In the past it was even encouraged as a way to include a test harness for every class. It is no longer considered to be best practices, but is something you may see. Suppose that we had a different `main` method in the Facility class for the previous example. Maybe that method simply produces a csv file report containing all the pets that have stayed in the previous 12 months. We would run that main method with `java Facility`.  


### Command Line Arguments

One way to get data into a program is to pass the information to the program when it is run. For a java program those command line arguments are put into an array and passed as a parameter to the main method.

The example below uses a for each loop to loop through the array and print out each element.  
```
public class CommandLineDemo {

	public static void main(String[] args) {
		for(String param: args){
			System.out.println(param);
		}
    System.out.println(args[0]);
	}
}
```
 Running this program with `java CommandLineDemo this is a demo` will result in the following output:
```
this
is
a
demo
this
```
*Note:  unlike C, Java does not include the name of the program as the first command line parameter.*

### Main is a class method

The main method in a class is always a [static or class method](/ooConcepts/classMembers).  This means that it cannot access any instance variables or instance methods directly, and must create an instance in order to use those methods.   

Persons new to Java programming often find this confusing and it is one of the reasons why all of the examples in this resource use a separate class to contain the main method. 

The example below shows a main method in a class and illustrates how instance methods must be used inside a static method.  [More on this topic can be found here](/ooConcepts/classMembers).

```
public class Pet{
    //instance variable for name
    private String name;

    // accessors and mutators for name   
    
    public void setName(String theName){
        name = theName;     
    }
    public String getName(){
        return name;       
    }
	public static void main(String[] args){
     //this next line won't work because name is an instance variable
     name = "fido"; //doesn't work
     
    //instead we need to create an instance
    Pet fido = new Pet();
    fido.setName("fido");
     
  
  }

}
```


 