---
title: Events in Programming
description: 
published: 1
date: 2022-08-17T19:42:10.564Z
tags: 
editor: markdown
dateCreated: 2022-08-17T18:13:49.939Z
---


# Events 

In the context of computer programming an **event** is a signal that indicates something has happened. The idea is very similar to the way humans use events to make decisions in their lives. Many people use the *event* of an alarm going off to signal that it is time to wake up in the morning. When one's body indicates it is hungry, that is an event that signals it is time to consume food.  When a notification (an event) is heard on a cell phone, the owner will pick up the cell phone and take action based on the type of notification.

### Signal-Response

When a computer process responds to an event with an appropriate action is sometimes referred to as **signal-response**. Signal-Response is a type of program design where the program wait for a sign (an event) and then responds with an action.  A signal-response  design allows the program to continue doing things while waiting for a signal, in much the same way that a human can continue on with their day even though their cell phone may or may not display a notification during the day. 

When the signal occurs, a reaction happens. After the reaction, the program resumes doing other things until the next signal.  In the same way that humans can react appropriately and differently to an alarm clock, a traffic light, and a phone call, a program can respond to multiple different signals (at different times).


### Signal-Response in OO

The **signal** is called an **event** in OO programming terms. The **response** is an invocation of a method that  causes the program to act appropriately given the signal.  The style of programming is known as **Event-driven programming** 
 - An event is an object that acts as a signal 
 - The sending of the signal (event)  is called **firing the event**
 - Often the event is fired by an interaction with system peripherals (e.g. keyboard, mouse, printer, stylus)
  - The response is invoked by the portion of the program that is paying attention to events.
  - The response portion of the program is known as a **listener** or **event handler**

### Event Driven Programming 
Creating a program to use an event-driven design requires the programmer to shift their perspective.  Instead of the algorithm for the overall program being the driving force of the design,  the response to different possible events is the primary design unit of the program.  In many ways the design of an event driven program is similar to the design of a web service that provides specific responses depending on which endpoint has been invoked.

1. In Event Driven programming the program no longer determines the order in which things can happen. 
    * the events that occur determine the order of operations
    * e.g. user clicks the red button before the blue button
2. In an event-driven program, the next thing that happens depends on the next event
    * This means that methods are defined that will never be explicitly invoked except for inside event handlers.
    * methods are invoked automatically when an event signals that the method needs to be called
3. Event driven programs cannot be written linearly


#### Event driven example

Event driven programs are often graphical, but they don't have to be. Any sort of action can trigger an event. The code below is an example of an event driven program.  It accepts input on the command line and generates an event every time the user presses the letter `w`.   The code includes two different listeners that consume the generated event.  The first listener prints a message when a `w` is printed.   The second listener incrementse a counter variable that represents the total number of `w`s pressed.   The program exits when the user presses the letter `x`.



```java

import java.util.EventObject;

class InputEvent extends EventObject {
    public InputEvent(Object source) {
        super(source);
    }
}
```
The `EventObject` is the event that is detected.

```java
interface InputListener {
    void inputReceived(InputEvent event);
}
```
```java
class PrintListener implements InputListener {
    @Override
    public void inputReceived(InputEvent event) {
        System.out.println("The letter 'w' was pressed!");
    }
}
```
```java
class CounterListener implements InputListener {
    private int counter = 0;

    @Override
    public void inputReceived(InputEvent event) {
        counter++;
        System.out.println("Total 'w' count: " + counter);
    }
}
```
The three classes above are the listeners that are called when the event is raised.  The interface class provides the polymorphic abstraction so that our implementation can use either the `PrintListener` or the `CounterListener` class.

```java
class InputNotifier {
    private InputListener listener;

    public void setInputListener(InputListener listener) {
        this.listener = listener;
    }

    public void notifyInputReceived(InputEvent event) {
        if (listener != null) {
            listener.inputReceived(event);
        }
    }
}
```
The `InputNotifier` class is the one that raises the events.   For simplicity, this notifier is only capable of managing one listener at a time.  Most classes that raise events can have multiple listeners attached.

```java
import java.util.Scanner;
public class EventDrivenProgram {
    public static void main(String[] args) {
        InputNotifier inputNotifier = new InputNotifier();
        PrintListener printListener = new PrintListener();
        CounterListener counterListener = new CounterListener();

        inputNotifier.setInputListener(printListener);
        inputNotifier.setInputListener(counterListener);

        Scanner scanner = new Scanner(System.in);
        String input;

        do {
            System.out.print("Enter input: ");
            input = scanner.nextLine();
            if (input.contains("w")) {
                inputNotifier.notifyInputReceived(new InputEvent(input));
            }
        } while (!input.equalsIgnoreCase("x"));

        System.out.println("Exiting the program...");
    }
}
```
