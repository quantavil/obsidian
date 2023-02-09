## TDD

_`TDD`_ is an iterative development process. Each iteration starts with a set of tests written for a new piece of functionality. These tests are supposed to fail during the start of iteration as there will be no application code corresponding to the tests. In the next phase of the iteration, Application code is written with an intention to pass all the tests written earlier in the iteration. Once the application code is ready tests are run.

![[Pasted image 20230207112025.png]]


### Benefits of TDD

1.  Unit test proves that the code actually works
2.  Can drive the design of the program
3.  Refactoring allows improving the design of the code
4.  Low-Level regression test suite
5.  Test first reduce the cost of the bugs

### Drawbacks of TDD

1.  Developer can consider it as a waste of time
2.  The test can be targeted on verification of classes and methods and not on what the code really should do
3.  Test become part of the maintenance overhead of a project
4.  Rewrite the test when requirements change


## ATDD
Acceptance Test-Driven Development (ATDD) methodology was a result of the natural evolution of TDD. It involves driving the entire application development by acceptance tests rather than requirement specifications to bring in the business analysts/customer perspective too.

![[Pasted image 20230207112704.png]]

### Benefits:

1.  `Better quality:` There is a reduction in the acceptance of test defects.
    
2.  `Better efficiency:` There is no code wastage in terms of excess modules.
    
3.  `Better confidence:` The business analyst is assured at each stage that the application is built as per their specifications.
    
4.  `Lesser documentation:` The acceptance tests and unit tests themselves serve as the specification documents. Also, there are no separate handover documents to be passed between business analysts and developers.

## Behavior Driven Development

Behavior Driven testing is an extension of TDD. Like in TDD in BDD also we write tests first and the add application code. The major difference that we get to see here are

-   _Tests are written in plain descriptive English type grammar_
-   _Tests are explained as behavior of application and are more user-focused_
-   _Using examples to clarify requirements_

This difference brings in the need to have a language that can define, in an understandable format.

## Features of BDD

1.  _Shifting from thinking in "`tests`" to thinking in "`behavior`"_
2.  _Collaboration between Business stakeholders, Business Analysts, QA Team and developers_
3.  _Ubiquitous language, it is easy to describe_
4.  _Allowing direct interaction with the developer’s code, but we write BDD tests in a language that can also be made out by business stakeholders._
5.   _Last but not least, acceptance tests can execute automatically, while business stakeholders manually perform it._



```ad-question
`Q: Behavior Driven Development is :`
*An Agile application development methodology* 


Explanation :
In software engineering, behavior-driven development is an Agile software development process that encourages collaboration among developers, QA and non-technical or business participants in a software project
```

## **The Cucumber Framework: BDD Framework for Selenium**

Cucumber BDD framework mainly consists of three major parts – **Feature File, Step Definitions**, and the **Test Runner File**.

### **1. Feature File**

A standalone unit or a single functionality (such as a login) for a project can be called a Feature. Each of these features will have scenarios that must be tested using Selenium integrated with Cucumber. A file that stores data about features, their descriptions, and the scenarios to be tested is called a **Feature File.**

Cucumber tests are written in these Feature Files that are stored with the extension – **“.feature”**. A Feature File can be given a description to make the documentation more legible.

```Gherkin
GIVEN user navigates to login page by opening Firefox
WHEN user enters correct <username> AND <password> values
THEN user is directed to the homepage
```

### **2. Step Definitions**

A Steps Definitions file stores the mapping data between each step of a scenario defined in the feature file and the code to be executed

```java
package StepDefinition;

public class Steps
{

@Given("^user navigates to the login page by opening Firefox$")
//Code to Open Firefox Browser and launch the login page of application to define the GIVEN step of the feature

@When("^user enters correct username and password values$")
//take inputs for username and password fields using find element by xpath. Put the correct username and password values as inputs to define the WHEN step of the feature

@Then (“^user gets directed to homepage$”)

//Direct to the Homepage of the application as a result of correct username and password inputs in the WHEN step. This would define the THEN step of the feature
```

### **3. Test Runner File**

To run the test, one needs a **Test Runner File**, which is a JUnit Test Runner Class containing the Step Definition location and the other primary metadata required to run the test.

The Test Runner File uses the **@RunWith()** Annotation from JUnit for executing tests. It also uses the **@CucumberOptions** Annotation to define the location of feature files, step definitions, reporting integrations, etc.

```java
package cucumberTest;

import org.junit.runner.RunWith;
import cucumber.api.CucumberOptions;
import cucumber.api.junit.Cucumber;

@RunWith(Cucumber.class)
@CucumberOptions(
features = "src/test/Feature"
,glue={"src/main/stepDefinition"}
,plugin={"html:src\\reports\\rep.html","junit:src\\reports\\rep1.xml","json:\\src\\reports\\rep2.json"
)

public class TestRunner {
}
```

### _`What is Cucumber?`_

_`Cucumber`_ is a testing framework which supports _`Behavior Driven Development (BDD)`_. It lets us define application behavior in plain meaningful English text using a simple grammar defined by a language called _`Gherkin`_. Cucumber itself is written in _`Ruby`_, but it can be used to “_`test`_” code written in _Ruby_ or other languages including but not limited to _Java_, _C#_ and _Python_.

```Gherkin
Feature: Update password

 Scenario: Admin user can update the user password

Given I am in the HR system with an Admin account
When I update password of another user
Then I receive a message for updating password successfully
And user password is updated to the new password
```

## Gherkin Keywords:

Gherkin is a line-oriented language in which every line has to start with a Gherkin keyword. They are:

- `Feature:` It is a list of scenarios
- `Scenario:` Business rule through a list of steps with arguments
- `Given:` Some precondition step
- `When:` Some key actions
- `Then:` To observe outcomes or validation
- `And,But:` To enumerate more Given, When, Then steps
- `Scenario Outline:` List of steps for data-driven as an Examples and `<placeholder>`
- `Examples`:  Container for table
- `Background:` List of steps run before each of the scenarios
- `""" (Doc Strings)`: This is used for representing strings
- `| (Data Tables):` This is used to present the data values in table form
- `@(Tags/Labels):`To group Scenarios 
- `<>` (placeholder)
- `#` For comments in Feature File

```Gherkin
Feature: Title of your feature
	I want to use this template for my feature file
@tag1
Scenario: Title of your scenario
Given I want to write a step with precondition
	And some other precondition
When I complete action
	And some other action
	And yet another action
Then I validate the outcomes
	And check more outcomes
@tag2
Scenario Outline: Title of your scenario outline
Given I want to write a step with <name>
When I check for the <value> in step
Then I verify the <status> in step
Examples:
    | name  |value | status |
    | name1 |  5   | success|
    | name2 |  7   | Fail   |

```
