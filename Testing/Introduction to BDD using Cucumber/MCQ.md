1. In software engineering, behavior-driven development is an Agile software development process that encourages collaboration among developers, QA and non-technical or business participants in a software project.
2. Feature file is written in : *Gherkin* is the format for cucumber specifications. It is a domain specific language which helps you to describe business requirements.
3. A Feature File is an entry point to the Cucumber tests. This is a file where you will describe your tests in Descriptive language. The feature file is the essential segment of cucumber tool, which is used to write acceptance steps for automation testing
4. Pick the correct statements with respect to step definition file.

	- [x] A step definition file can be created from the execution of feature file. 
	- [ ] All the step definitions should be given in a single file
	- [ ] Cucumber throws error if the step definition doesn't match with the Gherkin step
	- [x] Step definitions aren’t linked to a particular feature file or scenario 
	*Explanation* : On the execution of feature file, you will be able to generate step definition statements.

5. What is a runner class?

	- [ ] Runner class contains the main method to execute the test.
	- [x] In a runner class you can specify feature files to be picked up plus the steps definitions location,using some annotations. 
	- [ ] Runner class describes the test scenarios.
	- [x] Cucumber Uses Runner class of JUnit framework 
	Explanation : By the usage of tags, we can execute specified scenarios. we can also generate different type of reports

	Explanation : Runner class will use the Junit annotation @RunWith(), which tells JUnit what is the test runner class


---

1. If you are using multiple @Test annotations in a single JUnit file, and the methods c_test, a_test, and b_test are there which not arranged alphabetically in the code. Then in which sequence they will be executed?
  

The testrunner runs the methods in alphabetical order 

Depends as testrunner treats all methods to be independent of each other

Runs the methods in random order during each test run

All of the above