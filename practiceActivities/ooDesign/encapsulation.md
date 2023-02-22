---
title: Information Hiding/ Encapsulation
description: 
published: true
date: 2022-06-02T17:48:06.930Z
tags: 
editor: markdown
dateCreated: 2022-05-02T19:53:20.753Z
---

# Information Hiding/ Encapsulation

# Practice Activities for [Encapsulation](/ooDesign/encapsulation)



### Self Study Question
1. Consider the classes shown below.   How would you improve the encapsulation of these classes?

```
public class Client{
    public String name;
    public ArrayList<Order> orders = new ArrayList<Order>();
}
```

```
public class Order {
    public String number;

    public Order(String orderNumber){
        number = orderNumber;
    }
}
```

```
public class Runner{
    public static void main(String[] args){
        Client cOne = new Client();
        cOne.name = "Minnie";
        ArrayList<Order> cOrders = cOne.orders;
        Order temp = new Order("6540");
        cOrders.add(temp);
        temp = new Order("900021");
        cOrders.add(temp);
        temp = new Order("34");
        cOrders.add(temp);

        Client cTwo = new Client();
        cOrders = cTwo.orders;
        temp = new Order("832");
        cOrders.add(temp);
        temp = new Order("12");
        cOrders.add(temp);
        temp = new Order("006523");
        cOrders.add(temp);

        ArrayList<Client> clients = new ArrayList<Client>();
        clients.add(cOne);
        clients.add(cTwo);
  
        // print client orders and remove printed orders from list

        for(Client currentClient:clients){
            System.out.println("Orders from ");
            System.out.print(currentClient.name);
            System.out.println(":");
            cOrders = currentClient.orders;
            while (cOrders.size() > 0){
                System.out.println(cOrders.get(0).OrderNumber);
                orders.remove(0); 
            }
        }
 
    }
}
```

<details>
<summary>click here for one possible answer</summary>
  
- make instance variables private in `Client` and `Order`
- add public methods for setting and getting client name
- add public method for placing an order to `Client` that takes an order number and leaves the creation of the order to the Client class.
- add method to Order for getting the order number
- add a toString method to both classes
- add a printOrders method to `Client` that prints all current orders
- add a removeOrder method to `Client` that removes an order from the client's list.
</details>

---

The example on this wiki page was based on an example found here:https://github.com/dotnet/training-tutorials/blob/master/content/csharp/getting-started/encapsulation-oop.md