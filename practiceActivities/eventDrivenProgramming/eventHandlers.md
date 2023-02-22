---
title: Event Handlers
description: 
published: true
date: 2022-08-29T20:23:59.831Z
tags: 
editor: markdown
dateCreated: 2022-05-04T13:10:53.317Z
---

# Handling Events

# Practice Activities for [Event Handlers](/eventDrivenProgramming/eventHandlers)



### Self Study Questions
1. A way of responding to the event, is often called the what?
<details>
<summary>click here for one possible answer</summary>
  
Event handler.
</details>

2. What is the single method that must be implemented for the Action Listener interface?
<details>
<summary>click here for one possible answer</summary>
  
`actionPerformed(ActionEvent e).`
</details>

3. What is the Java code for a class called "closeProgramListener" that implements a listener to exit the program?
<details>
<summary>click here for one possible answer</summary>

	public  class closeProgramListener implements ActionListener{
    	public void actionPerformed(ActionEvent e){
        	System.exit(0);
    	} }

</details>

4. For **Lambda expressions** what is the operator that is used?
<details>
<summary>click here for one possible answer</summary>
  
`->`
</details>


### Practice Problem
Start with the `ExampleGui` and `ExampleController` classes shown below.   Add listeners to the buttons in the gui so that when the set string value button is clicked, the value shown in the text field is 'dinosaur'.     Use lambda notation for the listeners and event handler methods.    Be sure to let the `ExampleController` class manage the value of the string variable.

One solution to this practice problem can be found at `/course/practiceProblems/eventDrivenProgramming/eventPractice`  The starter code for this problem is shown below.

```java
package oointro;

/* When learning to write GUI applications I recommend using a * import.  
When you have the application set up it is best to get rid of the * import and just
include the classes you really use.   Most IDEs will do this for you.
*/

import javax.swing.*;
import java.awt.event.*;
import java.awt.*;

public class ExampleGui extends JFrame
{
	
	private ExampleController myController;

	public static final int WIDTH = 600;
	public static final int HEIGHT = 500;
	Container contentPane;
	/*if you need a component to be accessible to all 
	methods make it a member variable*/
	TextField globalTextField; 

	public ExampleGui(ExampleController theController)
	{
		super();
		myController = theController;
		setUpSize();
		setMainContainer();

	}

	private void setUpSize(){

		setSize(WIDTH, HEIGHT);
		setTitle("A Gui Example");
		setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);	
	}

//the next few methods set up the three panels used for the demo GUI
	private void setMainContainer(){
		contentPane = getContentPane();
        contentPane.setLayout(new BorderLayout());
        //note the nested function call
        contentPane.add(interactWithProgramPanel(), BorderLayout.CENTER);
	}

/* the  panel returned by this function is set up with buttons and additional panels 
which, in turn, have listeners that interact with the controller.  
In a more complex program the controller would get its data from a 
third class known as the 'model'   */
	private JPanel interactWithProgramPanel(){
	    JPanel examplePanel = new JPanel();
	    examplePanel.setLayout(new GridLayout(0,1));
	    globalTextField = new TextField("here there will be text");
		examplePanel.add(globalTextField);
		//more nested function calls
		examplePanel.add(showStringValueButton());
		examplePanel.add(setStringValueButton());
		return examplePanel;
	}

		private JButton showStringValueButton(){
		JButton exampleButton = new JButton("display current value of string value in controller/model");
		// add a listener to the button here. use methods if you can.
		return exampleButton;
	}

	private JButton setStringValueButton(){
		JButton exampleButton = new JButton("set string value of controller/model");
		// add a listener to the button here. use methods if you can.
		return exampleButton;
	}



/* event handler methods that might be useful  */

 private void changeString(String text){
 	myController.setString(text);

 }
 private void showString(){
 	globalTextField.setText(myController.toString());

 }
}
```
```java
package oointro;

public class ExampleController
{
    private String myString;


    public ExampleController(){
        myString = "this is a string";
    }

    public void setString(String ss){
        myString = ss;
    }
    @Override
    public String toString()
    {
        return myString;
    }

}
```