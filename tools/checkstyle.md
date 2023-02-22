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

Checkstyle is a command-line tool that can be used to determine if your source
code follows a set of style rules. It also checks for common programming
mistakes, such as class and method design problems.  Ensuring that aonsistent coding style is used throughout a project makes software much easier to maintain debug.

## Using Checkstyle
For this course checkstyle will be run as part of the gradle build process. The part in the gradle.build file that runs checkstyle is shown in the image below on line 3:

![image of the build.gradle file](/images/gradlecheckstyle.png)

Now that you can see how checkstyle is apart of the building process in this course, it is important to note that your project will be unable to build if there are checkstyle errors. Checkstyle uses an xml file to describe its style rules that you must follow in order for your project to build. That file is located here in your standard project hierarchy:

![image of the standard project hierarchy for the checkstyle.xml file](/images/xmlprojecthierarchy.png)

Checkstyle produces both comand line output, as well as nicely formatted output in an html file. The formatted html output can be located here:

![.image of the standard project hierarchy for the checkstyle HTML file](/images/checkstylehtmloutputhierarchy.png)

Below is an example of the Checkstyle html report output of a program you have been provided called *HelloWorld*: 

![image of checkstyle html report](/images/checkstylehtmlreport.png)

## Checkstyle without Gradle

Checkstyle can be run without gradle, but you won't need to do that for this course.  If you want to try it out, download the latest version as a JAR file from http://checkstyle.
sourceforge.net/. To run Checkstyle, move (or copy) the JAR file to the
same directory as your program. Open a terminal in that location, and run
the following command:

`java -jar checkstyle-*-all.jar -c /google_checks.xml *.java`





