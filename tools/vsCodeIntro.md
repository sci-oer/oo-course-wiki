---
title: Visual Studio Code
description: 
published: 1
date: 2022-08-17T18:50:15.192Z
tags: 
editor: markdown
dateCreated: 2022-08-17T18:16:31.758Z
---

# Visual Studio Code

**Visual Studio Code**, also commonly referred to as *VS Code*, is a lightweight but powerful source-code editor which can run on your desktop, made by Microsoft for most operating systems. Features include support for debugging, intelligent code completion, and code refactoring.

## Writing Code With VS Code
VS Code allows for you to write and edit source code. It comes packed with helpful tools such as **IntelliSense**, which consists of various code editing features including: code completion, parameter info, quick info, and member lists. It allows for you to compile and run code right in the terminal in the app. As well as manage your files for the project you are working on on the left side-bar. (See image below for these two features mentioned)

![code snippet in Virtual Studio Code of a hello world program.](/images/javavscode.png)

Another useful feature of VS Code is its ability to let you split screen your window. You can open as many editors as you like side by side vertically and horizontally. If you already have one editor open, there are multiple ways of opening another editor to the side of the current one such as:

- ⌘\ to split the active editor into two.
- Click the Split Editor button in the upper right of an editor.
- Drag and drop a file to any side of the editor region.

Below is an example of a split screen window in VS Code.

![split screen feature in Virtual Studio Code app.](/spliscreenvscode.png)

### Using InteliSense
This tool provides intelligent code completions based on language semantics and an analysis of your source code. If a language service, such as Java, knows possible completions, the IntelliSense suggestions will pop up as you type. Pressing `Tab` or `Enter` will insert the rest of the variable name, function, variable type, etc. 

![intellisense feature in Virtual Studio Code app.](/images/intellisense.png)

It also displayes quick info, provided by the language service, for each method by either hovering over the method or by clicking the info icon. This will provide helpful for understanding the methods you are using and understanding the parameters for it.

![method info feature Virtual Studio Code app.](/images/infovscode.png)

## Running Code With VS Code
![welcome page of the Virtual Studio Code app.](/images/getstarted_page.png)

This set of steps will start with the assumption that you have already opened your project code:
 
**Step 1 -** Click terminal option from menu above then click new terminal or use the `ctrl` and `~` keys to open a new terminal window.
 
**Step 2 -** If its a gradle folder (all the examples and projects for this course use gradle) Run`./gradle build` on the command line.

**Step 3 -** You code will be run and you should see your output form in the terminal window below.

#### Recorded Lecture

[Using VS Code with OER Resource](http://localhost:8000/lectures/tools/VSCode/)
