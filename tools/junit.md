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

![testingfiles.png](/testingfiles.png)
  
Gradle automatically runs junit tests when a program is built using gradle build.   The results are printed to the screen but also are written to the build folder in a `test-results` sub folder.   The XML file can be read by any text editor and most browsers.  

![testresultsjunit.png](/testresultsjunit.png)

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
The junit tests for this class methodically test each accessor and mutator.  Notice the use of `@Before` to identify a method that sets up the test objects for each test.  `Assert` is used to confirm that the values match the expected values.  The code shown below contains enough tests  for an example but does not represent exhaustive testing for the class.

```java
import org.junit.Test;
import org.junit.Before;
import org.junit.After;

import static org.junit.Assert.*;
public class AppointmentTest{
  private  Appointment appointment1;
  private Appointment appointment2;
  private Schedule schedule;

@Before public void startOver(){
    appointment1 = new Appointment();
    appointment2 = new Appointment("John Smith", "Monday");
    schedule = new Schedule();
  }

@Test public void constructorA(){
     assertNotNull(appointment1);
  }
 @Test public void constructorB(){
     assertNotNull(appointment2);
  }
 @Test public void constructorC(){
     appointment2 = null;
     appointment2 = new Appointment(null, null);
  }
  @Test public void gettersA(){
     assertEquals(appointment1.getName(), "none");
     assertEquals(appointment1.getDay(), "none");
  }
 @Test public void gettersB(){
     assertEquals(appointment2.getName(), "John Smith");
     assertEquals(appointment2.getDay(), "Monday");
  }
  @Test public void setters1(){
     appointment1.setName("Baron Snoopy");
     assertEquals(appointment1.getName(), "Baron Snoopy");
  }
 @Test public void setters2(){
     appointment1.setDay("Tuesday");
     assertEquals(appointment1.getDay(), "Tuesday");
  }
 @Test public void setters3(){
     appointment1.setName(null);
     assertNull(appointment1.getName());
}  
}
```

#### Recorded Lecture
[Using Junit](http://localhost:8000/lectures/tools/Junit/)