---
title: Using External Libraries
description: 
published: true
date: 2022-05-30T18:00:08.693Z
tags: 
editor: markdown
dateCreated: 2022-05-02T19:48:03.771Z
---

#### Prerequisite Knowledge
[Hello World](/java/helloWorld)
[Classes](/ooConcepts/classes)

# Using External Libraries

* A library of code is just a set of methods/procedures/classes that have been tested and made available for reuse.
* You will be using libraries of other people's code most of your career.  
* No one has the resources(time,money) to build and test and debug complex applications from scratch. 

A competent Java programmer must be able to work with the libraries.
- *You should:*
	- know some important classes by name;
  - know how to find out about other classes.
- *Need to know the programming interface, not the implementation.*


#### **Documentation**

* If you are using an open source library,  you can usually find documentation and examples on the website for the library.  

* The javadocs for a java library have all the details about how to use the classes.   
* Be sure you are using the javadocs that match the version of the library you are working with.    
* Sometimes you can: [find the javadocs online](http://localhost:8000/docs/api/index.html).
* Sometimes you have to generate them from source on your own.
		- See [Javadoc](/tools/javadocs) for info about how to use the javadoc tool

  
## Importing Library Classes

The import statement is how we take advantage of the many libraries available.

- Single classes may be imported:
`import java.util.ArrayList;
`
- Whole packages can be imported:
`import java.util.*;`


The `import` statement tells javac which classes and packages the program we are writing relies on.
`import java.util.Date;`
`import java.util.Random;`

You can just use the fully qualified names directly in the code if you don’t use an import statement.

i.e. `java.util.Random myVar = new java.util.Random();`

#### Import best practices
- Import fully qualified names only
  - `import java.util.ArrayList;`
  - not `import java.util.*;`
  - subpackages don’t import with * 
    - i.e. `java.util.* ` does not get you the classes in java.util.concurrent
- Arrange your imports by package
  - If you have more than one from the same package, put them together
  - Use alphabetical order or group by functionality/type

> Best practice is to import single classes 
{.is-info}
### Import != classpath

Import is a directive to the compiler about what class definitions you are using in your program. It makes your code more readable because it shortens the names you type.

Classpath specifies a location on a hard drive for the compiler and interpreter to go look for libraries and compiled files. Classpath is not specified in the soure code.

You need both.

### Packages
Packages are used to group classes that have similar functionality or context. Packages help us keep the code base organized and make it easier to avoid name collisions by having two classes with identical names.
For example, how many people have probably written a `Tree` class? Possibly even in the same program.  By using package names we can keep the various `Tree` classes organized
  - package a:  companyname.dstructures.Tree
  - package b: companyname.garden.Tree
  - Two different Tree classes!  no naming problems
  
Packages are realized by putting code in subfolders
The source code needs to have a package statement that matches the subfolder hierarchy.
`import companyname.dstructures.Tree;`



  