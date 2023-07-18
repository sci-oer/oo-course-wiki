---
title: Avoid duplicate code
description: 
published: 1
date: 2022-08-17T20:11:01.667Z
tags: 
editor: markdown
dateCreated: 2022-08-17T18:15:29.701Z
---

# OO Design Techniques

## Avoid/Remove Duplicate Code 

Novice programmers will often cut and paste code segments when they realize they need the same functionality in more than one place in their program. Often the only change is the data operated on by the copied code.

Duplicate code decreases cohesion because the same work is done in more than one place. It also makes  code maintenance harder. It can lead to the introduction of inconsistencies and errors during maintenance/modification.

Suppose that you've written a chunk of code that does a complicated calculation. The calculation is something that must be done for several different situations in the program.  In this scenario, suppose further that you duplicated the calculation code in the places that it was needed. Now suppose that the calculation requirements are changed and the code must be modified. The developer who makes those modifications must find every occurence of the cut/paste code in order to ensure that the software works properly.   

Duplicated code can cause inconsistencies in software because updates to the code may not be correctly applied to all copies.

The best way to avoid duplicate code is to use encapsulation. Create a method that provides the necessary computation. Use instance variables to maintain state. Use abstraction to create hierarchies of classes so that shared code is located in the parent class.

### Example - Duplicated Code:

The calculator example shown below has large quantities of duplicate code in each of the methods.  Duplicate code can be refactored into methods.

```java
import java.util.Scanner;

public class Calculator {
    private Scanner scanner;

    public Calculator() {
        scanner = new Scanner(System.in);
    }

    public void run() {
        int choice;
        System.out.println("Calculator Menu");
        System.out.println("1. Add");
        System.out.println("2. Subtract");
        System.out.println("3. Multiply");
        System.out.println("4. Divide");
        System.out.println("0. Exit");
        do {
            System.out.print("Enter your choice: ");
            choice = scanner.nextInt();

            switch (choice) {
                case 1:
                    performAddition();
                    break;
                case 2:
                    performSubtraction();
                    break;
                case 3:
                    performMultiplication();
                    break;
                case 4:
                    performDivision();
                    break;
                case 0:
                    System.out.println("Exiting...");
                    break;
                default:
                    System.out.println("Invalid choice. Please try again.");
            }

            System.out.println();
        } while (choice != 0);

        scanner.close();
    }

    private void performAddition() {
        System.out.print("Enter first number: ");
        double num1 = scanner.nextDouble();
        System.out.print("Enter second number: ");
        double num2 = scanner.nextDouble();
        double result = num1 + num2;
        System.out.println("Result: " + result);
        System.out.println("Calculator Menu");
        System.out.println("1. Add");
        System.out.println("2. Subtract");
        System.out.println("3. Multiply");
        System.out.println("4. Divide");
        System.out.println("0. Exit");
    }

    private void performSubtraction() {
        System.out.print("Enter first number: ");
        double num1 = scanner.nextDouble();
        System.out.print("Enter second number: ");
        double num2 = scanner.nextDouble();
        double result = num1 - num2;
        System.out.println("Result: " + result);
        System.out.println("Calculator Menu");
        System.out.println("1. Add");
        System.out.println("2. Subtract");
        System.out.println("3. Multiply");
        System.out.println("4. Divide");
        System.out.println("0. Exit");
    }

    private void performMultiplication() {
        System.out.print("Enter first number: ");
        double num1 = scanner.nextDouble();
        System.out.print("Enter second number: ");
        double num2 = scanner.nextDouble();
        double result = num1 * num2;
        System.out.println("Result: " + result);
        System.out.println("Calculator Menu");
        System.out.println("1. Add");
        System.out.println("2. Subtract");
        System.out.println("3. Multiply");
        System.out.println("4. Divide");
        System.out.println("0. Exit");
    }

    private void performDivision() {
        System.out.print("Enter first number: ");
        double num1 = scanner.nextDouble();
        System.out.print("Enter second number: ");
        double num2 = scanner.nextDouble();
        if (num2 != 0) {
            double result = num1 / num2;
            System.out.println("Result: " + result);
        } else {
            System.out.println("Cannot divide by zero!");
        }
        System.out.println("Calculator Menu");
        System.out.println("1. Add");
        System.out.println("2. Subtract");
        System.out.println("3. Multiply");
        System.out.println("4. Divide");
        System.out.println("0. Exit");
    }

    public static void main(String[] args) {
        Calculator calculator = new Calculator();
        calculator.run();
    }
}

```

After refactoring:

```java
import java.util.Scanner;

public class Calculator {
    private Scanner scanner;
    private double num1;
    private double num2;

    public Calculator() {
        scanner = new Scanner(System.in);
    }

    public void run() {
        int choice;

        do {
            displayMenu();
            System.out.print("Enter your choice: ");
            choice = scanner.nextInt();
            getUserInput();
            switch (choice) {
                case 1:
                    performAddition();
                    break;
                case 2:
                    performSubtraction();
                    break;
                case 3:
                    performMultiplication();
                    break;
                case 4:
                    performDivision();
                    break;
                case 0:
                    System.out.println("Exiting...");
                    break;
                default:
                    System.out.println("Invalid choice. Please try again.");
            }

            System.out.println();
        } while (choice != 0);

        scanner.close();
    }

    private void displayMenu() {
        System.out.println("Calculator Menu");
        System.out.println("1. Add");
        System.out.println("2. Subtract");
        System.out.println("3. Multiply");
        System.out.println("4. Divide");
        System.out.println("0. Exit");
    }

    private void getUserInput() {
        System.out.print("Enter first number: ");
        num1 = scanner.nextDouble();
        System.out.print("Enter second number: ");
        num2 = scanner.nextDouble();
    }

    private void performAddition() {
        double result = num1 + num2;
        System.out.println("Result: " + result);
    }

    private void performSubtraction() {
        double result = num1 - num2;
        System.out.println("Result: " + result);
    }

    private void performMultiplication() {
        double result = num1 * num2;
        System.out.println("Result: " + result);
    }

    private void performDivision() {
        if (num2 != 0) {
            double result = num1 / num2;
            System.out.println("Result: " + result);
        } else {
            System.out.println("Cannot divide by zero!");
        }
    }

    public static void main(String[] args) {
        Calculator calculator = new Calculator();
        calculator.run();
    }
}

```

The revised code uses methods for printing the menu and getting user input to avoid code duplication.  This could could be further improved by adding accessor and mutator methods for the newly introduced member variables `num1` and `num2`.

