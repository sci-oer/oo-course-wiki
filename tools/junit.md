---
title: Unit testing with JUnit
description: 
published: true
date: 2022-09-07T18:12:47.535Z
tags: 
editor: markdown
dateCreated: 2022-05-02T19:50:46.517Z
---

# JUnit

`JUnit` is a java library that provides automated tools for testing classes and java programs. It can be ran from the command line of your terminal but in this class we will be running `JUnit` from `Gradle`.

Like [Javadoc](/tools/javadocs), Junit uses the java annotation framework.  It reads annotations in code that is written as tests and uses those annotations to guide how those tests are run and how the results are captured.

One common method of using junit is to create a test class in parallel with each application class. The tests are included in the src tree but separated from the application classes as shown in the figure below.

![Standard gradle file/folder hierarchy shown with the src folder expanded. The src folder has two subfolders, main and test.   Those two subfolders have identical internal folder structures](/images/testingfiles.png)
  
Gradle automatically runs junit tests when a program is built using gradle build.   The results are printed to the screen but also are written to the build folder in a `test-results` sub folder.   The XML file can be read by any text editor and most browsers.  

![Standard gradle file/folder hierarchy shown with the build folder expanded. The test-results subfolder is circled to highlight where to look for junit test results.](/images/testresultsjunit.png)

If you need to compile your code without running the tests you can use the `-x` flag to gradle to exclude the test step.  `gradle -x test`


## Junit Annotations

  - Use `@Before, @After annotations` to denote methods that run before, or after, every test case. 
- A test case method must use @Test annotation
  `@Test(expected=IndexOutOfBoundsException.class)`
  `@Test(expectedArithmeticException)`
- Use `@Ignore` to ignore a test case that is not ready to be used as part of the test suite

  
## Example
The code shown below is for a simple class representing an appointment with a person.  Only the accessors and mutators are complete in the code shown.

```


public class Appointment{

	private String name;
	private String day;
	
	public Appointment(String name, String dayOfWeek){	
		setName(name)
		setDay(dayOfWeek)
	}
	
	public Appointment(){
		this("none","none");
	}
	
	public String getName(){
		return name;
	}
	
	public void setName(String personName){
		this.name = personName;
	}
	
	public String getDay(){
		return day;
	}
	
	public void setDay(String dayOfWeek){
		this.day = dayOfWeek;
	}
}
```
The junit tests for this class methodically test each accessor and mutator.  Notice the use of `@BeforeEach` to identify a method that sets up the test objects for each test. The static method `assertEquals` is used to confirm that the values match the expected values.  The code shown below contains enough tests  for an example but does not represent exhaustive testing for the class.



```java
import org.junit.jupiter.api.Assertions;
import org.junit.jupiter.api.BeforeEach;
import org.junit.jupiter.api.DisplayName;
import org.junit.jupiter.api.Test;

public class AppointmentTest {

    private Appointment appointment;

    @BeforeEach
    public void setup() {
        appointment = new Appointment();
    }

    @Test
    @DisplayName("Test default constructor")
    public void testDefaultConstructor() {
        Assertions.assertEquals("none", appointment.getName());
        Assertions.assertEquals("none", appointment.getDay());
    }

    @Test
    @DisplayName("Test parameterized constructor")
    public void testParameterizedConstructor() {
        Appointment appointment = new Appointment("John Doe", "Monday");
        Assertions.assertEquals("John Doe", appointment.getName());
        Assertions.assertEquals("Monday", appointment.getDay());
    }

    @Test
    @DisplayName("Test getName")
    public void testGetName() {
        appointment.setName("John Doe");
        Assertions.assertEquals("John Doe", appointment.getName());
    }

    @Test
    @DisplayName("Test setName")
    public void testSetName() {
        appointment.setName("John Doe");
        Assertions.assertEquals("John Doe", appointment.getName());
    }

    @Test
    @DisplayName("Test getDay")
    public void testGetDay() {
        appointment.setDay("Monday");
        Assertions.assertEquals("Monday", appointment.getDay());
    }

    @Test
    @DisplayName("Test setDay")
    public void testSetDay() {
        appointment.setDay("Monday");
        Assertions.assertEquals("Monday", appointment.getDay());
    }
}
```

These tests cover various scenarios such as testing the default constructor, the parameterized constructor, the getter and setter methods for `name` and `day`, and verifying the expected values.


