---
title: Event Handlers
description: 
published: 1
date: 2022-08-17T19:51:33.245Z
tags: listener, lambda
editor: markdown
dateCreated: 2022-08-17T18:13:47.374Z
---



# Handling Events
A program can only respond to events if it has been constructed in a way that it first knows an event has occured and then knows what to do if that event occurs. For example, a command line program to list all of the files in a directory (`ls`) has no need to respond to mouseclick events and, as such, has not been written to include an event handler for mouse clicks. A graphical editor, on the other hand, does need to respond to mouse clicks thus it is written with software components to interpret and react to the mouse.

An event can be used to change what a program is doing if the program has two components for each event it needs to respond to:
1. A way of recognizing the event, often called a **listener**
1. A way of responding to the event, often called an **event handler**.

In a Java program the *listener* part of the program should call the *handler* part of the program.   Some texts will teach that the *listener* is also the event handler, but that sort of design violates the [single responsiblity principle](/ooDesign/singleResponsibility) and reduces [cohesion](/ooDesign/cohesionCoupling).  For this course we will separate listener from handler.

### Listeners

A listener is an object that has the responsibility for interrupting the program when an event of a certain type has occured. A computer may be connected to a wide variety of peripherals and sensors such as mice, tablets, temperature sensors, keyboards and printers. When those peripherals send an event signal to the computer, it makes the events available to any program that is running. A listener is responsible for observing the events as they occur and causing the program to which it belongs to take the appropriate action.

In Java a listener is most often a subtype of the [EventListener](http://localhost:8000/docs/api/java.base/java/util/EventListener.html) interface. Also, since most Java programmers are introduced to event-driven programming via programming a GUI,  the most common event listener interface that novice programmers implement is the [ActionListener](http://localhost:8000/docs/api/java.desktop/java/awt/event/ActionListener.html).

The Action Listener interface has a single method that must be implemented `void actionPerformed​(ActionEvent e)`. When the Listener identifies the event it is listening for, it invokes the actionPerformed() method as the response to the event (the event handler).
Any class can implement the Listener interface, which means that any class can be used as a listener to an event.   

Components of a Java program that can generate events have a method that allows a listener to be connected to the component: `addActionListener(ActionListener listen)`.      The programmer must explicitly connect a listener to the component that generates events.  For example, suppose we were creating a program with a button that was intended to be clicked with a mouse to end the program.   One solution is to create a purpose-built listener class that encapsulates the desired action.

```java
	public  class EndProgramListener implements ActionListener{
		
		public void actionPerformed(ActionEvent e){
			System.exit(0);
		}
	}
```
Then, to connect the listener to the button we would use the following code:
```
		JButton endButton = new JButton("Click Me to End Program");
		endButton.addActionListener(new EndProgramListener());
```
Java handles the execution for us from there.  When the button is clicked, the actionPerformed method will be called, and the program will exit.

### Event Handlers

In many Java programs, including the example above, the *event handler*  is the `actionPerformed()` method. In many cases this approach works, but it can result in a program that lacks cohesion because often a single listener object will be programmed to handle multiple unrelated types of events.     A better way to ensure a well encapsulated program is to separate the event handling into a method.    For example,  the `EndProgramListener` shown earlier could be rewritten to call a specific method in the program, rather than making a system call.  This would ensure that the program had correctly closed any open streams before exiting.   This design means that the listener needs to be slightly more complex, but greatly improves encapsulation as the event handler now no longer needs to know anything about how to exit the program, it simply tells the program to end itself. 

```java
	public  class EndProgramListener implements ActionListener{
		GuiProgramClass myProgram;
    
    public EndProgramListener(GuiProgramClass prog){
       myProgram = prog;
    }
		public void actionPerformed(ActionEvent e){
			myProgram.end();
		}
	}
```
The code to assign such a listener to the button would change only slightly as it would need to send in a reference to the program.
```
		JButton endButton = new JButton("Click Me to End Program");
		endButton.addActionListener(new EndProgramListener(this)); //reference to program -->this
```

The past several versions of Java have provided a streamlined mechanism for assigning event handlers to components through the use of **Lambda expressions** and **Functional Interfaces**.   A complete knowledge of those terms is unnecessary to take advantage of the technique.

A lambda expression makes use of an operator `->` that tells Java to take a specific action if an event occurs. 
The syntax shown below accomplishes the same goals as the earlier example, but there is no need for a specific ActionListener class type.  Instead the `program.end()` method is called by the lambda expression.

```
		JButton endButton = new JButton("Click Me to End Program");
		endButton.addActionListener(ev -> prog.end());
```
The use of [lambda expressions](/functionalProgramming/lambdaListeners) to add listeners to a GUI component can greatly increase cohesion and reduce coupling.   

