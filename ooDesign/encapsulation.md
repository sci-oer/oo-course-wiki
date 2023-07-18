---
title: Information Hiding/ Encapsulation
description: 
published: 1
date: 2022-08-17T19:35:24.334Z
tags: 
editor: markdown
dateCreated: 2022-08-17T18:15:32.147Z
---


# Information Hiding/ Encapsulation

**Abstraction and encapsulation are often confused:**

- Abstraction has to do with hiding details at a **design** level  
    - Classes and subclasses
    - Interfaces
- Encapsulation is the process of hiding details at  **implementation** level 
    - for example: the details of how ArrayList.add() is implemented are not necessary to use the method





Encapsulation is a fundamental concept in object-oriented programming (OOP) that promotes data hiding and ensures the integrity of an object's internal state. It allows objects to control access to their data by providing a well-defined interface, preventing external code from directly manipulating the internal state.  By encapsulating data, we restrict direct access to it from external code, enforcing the principle of information hiding.

Benefits of Encapsulation:
1. Data Protection: Encapsulation ensures that data is not directly accessible from outside the object, preventing unauthorized modifications and ensuring data integrity.
2. Modularity and Maintainability: Encapsulating data and behavior within a class promotes modularity, allowing easier maintenance and updates without affecting other parts of the program.
3. Code Reusability: Encapsulated classes can be reused in different contexts without worrying about their internal implementation details, leading to cleaner and more flexible code.
4. Enhanced Security: Encapsulation prevents unauthorized access to sensitive data and provides controlled access through well-defined methods, reducing security risks.


## Effective Encapsulation
In an OO program, computation is achieved by passing messages between objects (method calls). A well encapsulated OO program is organized as a system of classes that ensure that their data fields are inaccessible to client applications while providing methods to access and mutate, where appropriate, those data fields or values that result from computations on those data fields.

Encapsulation can be accomplished through the use of design approaches such as: 
   - private variables
   - private helper methods
   - public methods for all operations required to use the class
   - including toString and equals
   - restricting the public API to only required methods
   

Java provides mechanisms to achieve encapsulation: access modifiers and getter and setter methods.

1. Access Modifiers:
Java offers four access modifiers: public, protected, default (package-private), and private. These modifiers control the visibility of class members, such as fields and methods, within and outside the class.

- Public: Public members are accessible from anywhere in the program.
- Protected: Protected members are accessible within the same package and subclasses, even if they belong to different packages.
- Default: Default members are accessible within the same package only.
- Private: Private members are accessible only within the same class.

2. Getter and Setter Methods:
Getter and setter methods allow controlled access to the private members of a class, enabling read and write operations, respectively. They provide an interface through which the object's internal state can be accessed and modified, while maintaining encapsulation.

Example: Encapsulating a Bank Account Class

```java
public class BankAccount {
    private String accountNumber;
    private double balance;

    public String getAccountNumber() {
        return accountNumber;
    }

    public void setAccountNumber(String accountNumber) {
        this.accountNumber = accountNumber;
    }

    public double getBalance() {
        return balance;
    }

    public void deposit(double amount) {
        balance += amount;
    }

    public void withdraw(double amount) {
        if (amount <= balance) {
            balance -= amount;
        } else {
            System.out.println("Insufficient funds.");
        }
    }
}
```

In the example above, the `BankAccount` class encapsulates the account number and balance. The fields `accountNumber` and `balance` are marked as private, preventing direct access from external code. The class provides getter methods (`getAccountNumber()` and `getBalance()`) to read the account number and balance, respectively. The setter method (`setAccountNumber()`) allows the account number to be modified. Additionally, the class includes methods for depositing (`deposit()`) and withdrawing (`withdraw()`) funds, which manipulate the `balance` field while maintaining control over the internal state.

Including the `toString()` and `equals()` methods in a Java class can indirectly contribute to encapsulation.

1. `toString()` method:

The `toString()` method is used to provide a string representation of an object. By overriding this method in a class, you can define how the object should be represented as a string when it is printed or concatenated with other strings. 
By providing a meaningful `toString()` implementation, you can encapsulate the internal state of the object within the class. Instead of directly exposing the internal fields, you can choose to display a concise and informative string representation of the object's state. This way, the internal details remain hidden from external code, promoting encapsulation.

2. `equals()` method:

The `equals()` method is used to compare two objects for equality. By overriding this method in a class, you can define the criteria for determining whether two instances of the class are considered equal.

The `equals()` method affects encapsulation by allowing you to define equality based on specific fields or properties of the object. In this way, you can encapsulate the equality logic within the class itself, rather than relying on external code to compare individual fields. This approach ensures that the internal representation and behavior of the class remain encapsulated and consistent.

Furthermore, when overriding `equals()`, it is recommended to also override the `hashCode()` method, which generates a unique integer representation for the object. These methods work together to ensure consistency when the object is used in hash-based collections such as HashMap or HashSet.

