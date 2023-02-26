---
title: JavaDocs
description: 
published: true
date: 2022-08-22T15:59:18.558Z
tags: 
editor: markdown
dateCreated: 2022-05-02T19:50:41.656Z
---

# Javadocs

> The javadocs for a java library have all the details about how to use the classes.   This interactive resource includes a copy of [the java language documentation ](http://localhost:8000/docs)
> {.is-success}

Javadoc comments are annotations to the source code for a program that can be used by the javadoc tool to produce human readable documentation. 

Javadocs are supported by the annotations feature of the java programming language. Annotations are preceded by the @ symbol.   Specific annotations are used by the Javadoc program to produce documentation for your program. This documentation provides the reader a description of how to use a specific class in a program. Things that are included in this description are; the purpose, parameters and return values for every public method in the class. The description should also include a general overview of the class and its purpose. Here is a simpiler example for the String class:

![Screenshot of the first constructor documentation found here: http://localhost:8000/docs/api/java.base/java/lang/String.html](/images/stringdocumentation.png)

## Creating javadoc comments

By convention, every public method in a java program should javadoc comments.  As a minimum the method should have a sentence or two that describe the purpose of the method and information about the parameters to the method and the return values of the method.



.

```
/**
 General Comments about the method . . .
 @param aParameter Description of aParameter
 @return What is returned
 . . .
*/
```




- `@` tags should be placed in the order found below
- If there are multiple parameters, each should have its own `@param` on a separate line, and each should be listed according to its left-to-right order on the parameter list
- If there are multiple authors, each should have its own `@author` on a separate line
```
@param Parameter_Name Parameter_Description
@return Description_Of_Value_Returned
@throws Exception_Type Explanation
@deprecated
@see Package_Name.Class_Name
@author Author
@version Version_Information
```

## Creating JavaDocs documentation

##### Using Gradle
- The java task in gradle provides tools for generating javadocs from the appropriate comments.  To use gradle to generate javadoc documentation you simply type `gradle javadoc` on the command line.  Gradle will put the documentation inside the `build` folder in a subfolder called `docs`.

![File Folder hierachy showing with the build folder expanded and the docs subfolder circled. The javadoc sub folder of the docs folder is visible](/images/javadocs.png)

##### Without using Gradle  
- To run javadoc on a package
  - `javadoc –d Documentation_Directory Package_Name`
  - The HTML documents produced will be placed in the `Documentation_Directory`
  - If the `–d` and `Documentation_Directory` are omitted javadoc uses default settings
- javadoc on a single class
	- `javadoc ClassName.java`
- all the classes in a directory, give the following command instead
	- `javadoc *.java`



## Javadocs for Parameterized classes
- The documentation for a parametarized class, like the ```ArrayList```  includes a generic  type parameter:
	`ArrayList<E>`
  
- The same type parameter reappears in the parameter lists and return types of the methods of the class:
	`E get(int index)`
	`boolean add(E e)`
  
- The types in the documentation are placeholders for the types we use in in our implementation
  	- An `ArrayList<Track>` actually has methods:
        - `Track get(int index)`
        - `boolean add(Track e)`
  

