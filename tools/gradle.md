---
title: Gradle
description: 
published: true
date: 2022-08-22T15:02:45.777Z
tags: 
editor: markdown
dateCreated: 2022-05-02T19:50:37.040Z
---

# Gradle

Gradle is a build automation tool known for its flexibility to build software. Gradle is used to automate the creation of applications. The building process includes compiling, linking, and packaging Java code. 

## Using Gradle
Gradle is a program that must be installed on your computer, but in regards to this course it has already been installed in the docker container. Gradle works by reading a file that contains the instructions for each build process. Here is where the Gradle file is in the project hierarchy:

![shows the file/folder structure for a standard gradle project.  The build.gradle file is at the root.  Subfolders include config and src. The README for the project is also at the root](/images/gradlehierarchy.png)

Here is what that file looks like:

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
test {
    useJUnitPlatform()
}

//change the name of the class that is run on line 16 to match your own code
task echo;
echo.doFirst {
    println "To run the program:\njava -cp build/classes/java/main somepackagename.JavaClass"
}

dependencies {
    testImplementation 'org.junit.jupiter:junit-jupiter-api:5.7.2'
    testRuntimeOnly 'org.junit.jupiter:junit-jupiter-engine:5.7.2'

}
```

Gradle can be run from the command line or from an IDE.  Sometimes an IDE will make changes to your gradle.build file, so use the IDE only if you understand what it is doing.

## Running Gradle on the Command Line
To run gradle on the command line, simply type `gradle build`.   If your code compiles without errors you should see output something like the following:

```
starterFiles $gradle build

BUILD SUCCESSFUL in 280ms
3 actionable tasks: 3 up-to-date
starterFiles $
```

Our example gradle file provides a specialized task called `echo` that echos the command needed to run the program as output so that it is easy to cut/paste the command and run the program.  It is worth noting that `echo` is not a built in command for gradle and it does not run the program.   It is simply a convenience task used by the authors.

The output from running `echo` is shown below.

```
starterFiles $gradle echo

> Task :echo
To run the program:
java -cp build/classes/java/main somepackagename.JavaClass

BUILD SUCCESSFUL in 283ms
1 actionable task: 1 executed
starterFiles $

```

## GradleW

GradleW is a wrapper program used to ensure that there are no versioning issues with shared repositories using gradle.  It is invaluable in a production environment where many developers work in the same codebase.  

There are advantages to using the wrapper for team projects as it removes the requirement for gradle to be installed on the developers machine. However, it adds enough size to the repository that it is impractical for a teaching situation where hundreds of similar repositories must be downloaded to the computer of the person doing the grading.    

Because of the size added by gradlew, for this class we're going to stick with using the installed version of gradle.  It is already installed in the docker container so you don't have to install on your host computer.
> Under **NO** circumstances, should you be adding gradlew and its associated files to your assignment submissions.
{.is-warning}
