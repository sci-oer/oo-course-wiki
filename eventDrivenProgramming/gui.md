---
title: Graphical User Interfaces
description: 
published: 1
date: 2022-08-17T19:40:21.113Z
tags: 
editor: markdown
dateCreated: 2022-08-17T18:13:52.456Z
---

# Graphical User Interfaces

GUI programming is the most common example of event driven programming. 

To ensure good encapsulation, the program should work without the GUI (perhaps as an API or via a command line interface). The GUI should be a layer that provides a visual representation of the already functional program.

A GUI is built up incrementally from  components that are layered  and arranged to make the display that the user sees. The libraries and framework chosen dictate the names of the components and the methods they have available.  All GUI frameworks are similar in functionality provided. 

![Components layered to make a simple GUI consisting of a text field, two buttons, a text area and a label. ](/images/guiComponents.png)

In the image shown there are several layers of components. There is a panel that is outlined in red. The Panel contains the field with the words 'text field' as well as a second panel to the left that contains the 'button' and another field labelled 'text'. Finally there is a second button at the bottom of the panel.

Each component is added separately to the container to create the desired user interface.

## WireFrames and Planning
It is helpful to make a prototype of the GUI so that you know what components you need.  A wireframe is one simple way to make a prototype.  A wireframe is a simple line drawing that indicates where the fields, buttons, and menus will be on a user interface.  There are many specialized applications for creating wire frames but any drawing tool can be used, or a wireframe can be sketched by hand.

![Example wireframe of possible interface for uploading files that includes multiple tabs as well as some check boxes for file characteristcs. ](/images/wireFrame.png)

## GUI programming with SWING
A SWING gui is created by adding *components* to a *container* and arranging them with a *layout manager*.  Because containers are also components, the programmer can create a multi-layer view that consists of containers that hold other containers which are in turn holding base components.

### Components

A programmer can create custom components, but the [components provided with SWING](http://localhost:8000/docs/api/java.desktop/javax/swing/JComponent.html) are more than sufficient for learning to program an event driven GUI.    Some of the commonly used components are shown in the images below.

![ A column of swing components including JButton, JCheckbox, JRadioButton, JSlider, JSpinner, and JCombobox](/images/componentsone.png) &nbsp; &nbsp; &nbsp;&nbsp; &nbsp; ![A column of swing components including JMenuBar, JTextArea, JList, JTextField, JPasswordField and JLabel.](/images/componentstwo.png)

When desiging a GUI it is important to choose the component that is best suited for the operation needed. For example, a radio button set is used when the user may make a single choice from a list of choices, but a checkbox set is used when the user may select multiple choices.


### Containers
The two containers that are used most often are the [JPanel](http://localhost:8000/docs/api/java.desktop/javax/swing/JPanel.html) and the [JScrollPane](http://localhost:8000/docs/api/java.desktop/javax/swing/JScrollPane.html).    

The root container for a SWING application is a [JFrame](http://localhost:8000/docs/api/java.desktop/javax/swing/JFrame.html).   The JFrame class has methods for adding titles and size constraints to the application. The `JFrame` class has an embedded [`ContentPane`](http://localhost:8000/docs/api/java.desktop/java/awt/Container.html) which acts as the base layer for all other containers and components.  The content pane is accessed through the `getContentPane()` method.

### Layout Managers

In a SWING gui, a layout manger is used to arrange components to form a usable GUI. The prorammer does not explicitly set x/y coordinates for each element of the gui. Instead the location of the element is set in relation to other elements and the actual location is calculated on the fly by the program. This permits a GUI to resize, and to be visible on a variety of monitor sizes and at different resolutions.

There are a number of layout manager classes including
[BorderLayout](http://localhost:8000/docs/api/java.desktop/java/awt/BorderLayout.html),  [CardLayout](http://localhost:8000/docs/api/java.desktop/java/awt/CardLayout.html), [FlowLayout](http://localhost:8000/docs/api/java.desktop/java/awt/FlowLayout.html), and [GridLayout](http://localhost:8000/docs/api/java.desktop/java/awt/GridLayout.html)

### Example Swing Gui
The code for a small GUI application is shown below. After the code are screenshots of the application as written using the `BorderLayout` manager and again when the BorderLayout for the contentPane and the text field panel is changed to `FlowLayout` (lines 22 and 62). It is easy to see from the screenshots what dramatic effect the choice of layout manager can have.
```java
public class SampleGuiComponentDemo extends JFrame
{
	
	public static final int WIDTH = 900;
	public static final int HEIGHT = 500;
	
	private TextArea textToWrite;  //GUIs can have member variables
	private TextField stringAdd;
	private TextField numberAdd;

	public SampleGuiComponentDemo()
	{
		super();
		setSize(WIDTH, HEIGHT);
		stringAdd = new TextField();
		numberAdd = new TextField();

		setTitle("SampleGui");
		setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

		Container contentPane = getContentPane();
    contentPane.setLayout(new BorderLayout());
    contentPane.add(new JLabel("Border Layout on contentPane"));
        
		add(setupAddToPanel(),BorderLayout.WEST);
	 	add(setupButtonPanel(),BorderLayout.EAST);
		add(setTextAreaPanel(),BorderLayout.CENTER);
		pack();
	}
	

	private JPanel setupButtonPanel(){
		JPanel buttonPanel = new JPanel();
		buttonPanel.setLayout(new BoxLayout(buttonPanel, BoxLayout.PAGE_AXIS));
		buttonPanel.setBorder(BorderFactory.createLineBorder(Color.black));

		buttonPanel.add(new JLabel("Box Layout on Button Panel"));
		JButton buttonOne = new JButton("ButtonOne");
		buttonPanel.add(buttonOne);
		JButton buttonTwo = new JButton("ButtonTwo");
		buttonPanel.add(buttonTwo);

		return buttonPanel;
	}
	private JPanel setTextAreaPanel(){
		JPanel viewPanel = new JPanel();
		viewPanel.setLayout(new BorderLayout());
		viewPanel.setBorder(BorderFactory.createLineBorder(Color.red));
		viewPanel.add(new JLabel("Border Layout on Text Area Panel"), BorderLayout.NORTH);
		textToWrite = new TextArea(15,40);
		textToWrite.setEditable(false);
		textToWrite.setText("TextArea: BorderLayout: Center");
		viewPanel.add(textToWrite, BorderLayout.CENTER);
		return viewPanel;
	}

	private  JPanel setupAddToPanel()
	{
		JPanel addThings = new JPanel();
		addThings.setBorder(BorderFactory.createLineBorder(Color.blue));

		addThings.setLayout(new BoxLayout(addThings, BoxLayout.PAGE_AXIS));;
		addThings.add(new Label("BoxLayout on Panel"));
		addThings.add(new Label("Type a string here"));
		addThings.add(stringAdd);
		addThings.add(new Label("type a number here"));
		addThings.add(numberAdd);
		JButton submitButton = new JButton("Submit");
		addThings.add(submitButton);
		return(addThings);
	}
}
```
The habit of separating the setup code into private methods that return a component makes the GUI program much more readable.   

#### Sample GUI as written with BorderLayout

![Sample Gui rendered using Border Layout](/images/sampleguiborderlayout.png)

#### Sample GUI with FlowLayout

![Sample Gui rendered using Flow Layout](/images/sampleguiflowlayout.png)


This example GUI contains no code for handling events. The *event handlers* must be added as listeners to any component that needs to react to use input. This is demonstrated in the [Event Handlers](/eventDrivenProgramming/eventHandlers) section of the wiki.



