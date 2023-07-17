---
title: Using Checkstyle
description: 
published: true
date: 2022-08-29T19:58:08.803Z
tags: 
editor: markdown
dateCreated: 2022-05-02T19:50:32.152Z
---

# Checkstyle

Checkstyle is a command-line tool that can be used to determine if your source code follows a set of style rules. It also checks for common programming mistakes, such as class and method design problems.  Ensuring that aonsistent coding style is used throughout a project makes software much easier to maintain debug.

## Using Checkstyle
One common way to use checkstyle is as part of the gradle build process. The part in the gradle.build file that runs checkstyle is shown in the image below on line 3:

```groovy
plugins {
    id 'java'
    id 'checkstyle'
}

sourceCompatibility = 1.11
targetCompatibility = 1.11

repositories {
    mavenCentral()
}

//change the name of the class that is run on line 16 to match your own code
task echo;
run.doFirst {
    println "To run the program:\njava -cp build/classes/java/main somepackagename.JavaClass"
}


```
Now that you can see how checkstyle is apart of the building process in this course, it is important to note that your project will be unable to build if there are checkstyle errors. Checkstyle uses an xml file to describe its style rules that you must follow in order for your project to build. That file is located in your standard project hierarchy:

![image of the standard project hierarchy showing the checkstyle.xml file in the config/checkstyle folder](/images/xmlprojecthierarchy.png)

Checkstyle produces both comand line output, as well as nicely formatted output in an html file. The formatted html output can be located in the build/reports folder of the file hierarchy.

![.image of the standard project hierarchy showing the checkstyle HTML file in the build/reports/checkstyle folder](/images/checkstylehtmloutputhierarchy.png)

Below is an example of the Checkstyle html report output of a program you have been provided called *HelloWorld*: 

![screenshot of a sample checkstyle html file from the build/reports/checkstyle folder](/images/checkstylehtmlreport.png)

## Checkstyle without Gradle

Checkstyle can be run without gradle if desired.  If you want to try that out, download the latest version as a JAR file from `http://checkstyle.sourceforge.net/`. To run Checkstyle, move (or copy) the JAR file to the same directory as your program. Open a terminal in that location, and run the following command:

`java -jar checkstyle-*-all.jar -c /google_checks.xml *.java`






