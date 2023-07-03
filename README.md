## Folder Structure

```
selenium_javaFramework
|   excels
|   logoAndSvgs
|   logs
|   reports 
└─── src
|	 └─── main
|	 |    └─── java
|	 |    |    └─── PageObjects
|	 |    |	        └─── FrontOffice
|	 |    |	        |       | LoginPage.java
|	 |    |         └─── BackOffice  
|	 |    |	        └─── Utils
|	 |    |	        |       | ExcelReader.java
|	 |    |	        |       | ExtentManager.java
|	 |    |         |       | ExtentTestManager.java
|	 |    |         |       | Helper
|	 └─── test
|	 |    └─── java
|	 |    |    └─── tests
|	 |    |    |    └─── Listener
|	 |    |    |            | AnnotationTransformer.java
|	 |    |    |            | GroupedLoggingAppender.java
|	 |    |    |            | ListenerClass.java
|	 |    |    |            | Retry.java
|	 |    |    |            | TestListener.java
|	 |    |    |            | WebDriverListener.java 
|	 |    |    |    └─── loginTest
|	 |    |    |            | BaseLogin.java
|	 |    |    |            | DataProviderClass.java
|	 |    |    |            | Setup.java
| 	suiteXml
|   videos
|   .gitignore
|   pom.xml 
```

# Introduction:

A Data-Driven Selenium Java's automation framework for web automation Testing.

# Project Execution Guidelines:

1. Clone Git Repository 'git clone {repoURL}'
2. Run command 'mvn clean test -DsuiteXmlFile="suitexml/config/testNg.xml"'

# Installation and Setup Guidelines:

1. To Install the JDK Software and Set JAVA_HOME on a Windows System
2. Install the JDK software.
   -> Go to http://java.sun.com/javase/downloads/index.jsp.
   -> Select the appropriate JDK software and click Download.
   The JDK software is installed on your computer, for example,
   at C:\Program Files\Java\jdk1.6.0_02. You can move the JDK software to another location if desired.
3. Set JAVA_HOME:
   -> Right-click My Computer and select Properties.
   -> On the Advanced tab, select Environment Variables, and then edit JAVA_HOME
   to point to where the JDK software is located, for example, C:\Program Files\Java\jdk1.6.0_02.
4. Set MAVEN_HOME
   -> Right-click My Computer and select Properties.
   -> On the Advanced tab, select Environment Variables, and then edit MAVEN_HOME to point to where
      the Maven software is located, for example, C:\Program Files\apache-maven-3.9.1
5. IDE Install (Intellij and Eclipse)
   Eclipse IDE https://www.eclipse.org/downloads/
   Intellij IDE https://www.jetbrains.com/idea/download/#section=windows

# src/main/java/Utils/ExcelReader :

The provided code defines a class named ExcelReader in the Utils package, which includes methods to read
data from an Excel file using Apache POI.

# src/main/java/Utils/ExtentManager :
The provided code defines a class named ExtentManager that is responsible for managing the creation
and retrieval of an ExtentReports instance from the ExtentReports library. (i.e, to generate HTML report).

# src/main/java/Utils/ExtentTestManager :
The provided code defines a class named ExtentTestManager that manages the creation and retrieval of ExtentTest
instances from the ExtentReports library. Here's a breakdown of the code:

# src/main/java/Utils/Helper :
The Helper class has several static variables including prop of type Properties, dataFolderBasePath representing the
base path for data files, random of type Random, and webDriver of type ThreadLocal<WebDriver>.

The readConfig method is responsible for reading a configuration file in XML format. It takes the configFileName
as a parameter and loads the XML file using FileInputStream and prop.loadFromXML().

The takeScreenShot method captures a screenshot using Selenium's TakesScreenshot interface.
It saves the screenshot file to a specified location and returns the file path.

The waitForPageToBeReady method waits for the page to be fully loaded by executing
JavaScript code to check the document's ready state.

The getDriver and setWebDriver methods are used to get and set the WebDriver instance respectively.
They utilize ThreadLocal to store the WebDriver instance separately for each thread.

Overall, this Helper class provides various utility methods for handling configuration files,
taking screenshots, waiting for page load, and managing the WebDriver instance.

# src/test/java/tests/listener/AnnotationTransformer :

The AnnotationTransformer class is defined, and it implements the IAnnotationTransformer interface.

The transform method is an overridden method from the IAnnotationTransformer interface.
It is responsible for modifying the test annotation at runtime. In this implementation,
it sets the retry analyzer for the test annotation to Retry.class.

The setRetryAnalyzer method allows you to specify a class that implements the IRetryAnalyzer
interface to handle test retries. In this case, the Retry class is being set as the retry
analyzer for the test annotation.

By using this AnnotationTransformer class, you can customize the behavior of test annotations,
such as enabling test retries, by implementing the necessary logic in the transform method.


# src/test/java/tests/listener/GroupedLoggingAppender :

Overall, the GroupedLoggingAppender class provides functionality to log events from different
threads into separate log files and merge them into a single log file during report generation.

# src/test/java/tests/listener/ListenerClass :

Overall, the ListenerClass serves as a TestNG listener that interacts with the Extent Reports
framework to log test statuses and perform certain operations at different stages of the test execution lifecycle.


# src/test/java/tests/listener/Retry :

Overall, the Retry class provides a mechanism for retrying failed tests and capturing additional
information for reporting purposes using the Extent Reports framework.

# src/test/java/tests/listener/TestListener :

This TestListener class provides additional functionality for logging test results and capturing
screenshots compared to the base implementation in the TestListenerAdapter class.

Note: ListenerClass and TestListener class are similar with similar functionality.
Optimize TestListener class and remove Listener class in the future.

# src/test/java/tests/listener/WebDriverListener :

The WebDriverListener class is responsible for setting up the WebDriver instance before each test
method and can be used to perform any additional actions required before or after method invocations.

# suiteXml :

A suiteXml is a folder where configuration file is added to load invoke the data and configure the testsuite.

# suiteXml/test-data.xml :

A test-data.xml file contains credentials that is used for system login i.e, baseURL, username and password
and other credentials.

# suiteXml/testNg.xml :

A testNg.xml file is a configuration file that helps in organizing our tests.
It allows to create and handle multiple test classes, define test suites and tests.

# logs :

A logs folder helps us to track and log the test steps.

# reports :

A reports is a folder where each time test execution report is dumped, this is an .html
file which can be viewed via browsers.

# .gitignore :

A git configuration file that excludes specific directory or files from
being included during commits to a git repository.

# pom.xml :

Maven related file used for managing dependency and plugins with in the
project.


