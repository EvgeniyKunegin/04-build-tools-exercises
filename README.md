#### This project is for the Devops bootcamp exercise for 
#### "Build Tools and Package Managers" 

Your team wants to build out a small helper library in Java and ask you to take over the project.




EXERCISE 0: Clone project and create own Git repository

To work with the project for the exercises:

- Clone the project and
- create your own project/git repository from it




EXERCISE 1: Build jar artifact

You want to deploy the artifact to share that library with all team members. So:

- try to build the jar file
The Build will fail, because of a compile error in a test, so you can't build the jar. 

```
gradle build

error: incompatible types: String cannot be converted to boolean
        boolean result = myApp.getCondition("true");
```




EXERCISE 2: Run tests

- Fix the test, by changing "true" string to true boolean.
- Run gradle test to execute only the tests and check the fix.

```
boolean result = myApp.getCondition(Boolean.parseBoolean("true"));
```

```
gradle test
```


EXERCISE 3: Clean and build App

You fixed the test. Now:

- clean the build folder with gradle clean and
- try to build jar file again.
```
gradle clean
gradle build
```
BUILD SUCCESSFUL in 1s




EXERCISE 4: Start application

Start the jar file to test that the application runs successfully as a jar file

- Start app with java -jar app-1.0.jar
NOTE: replace "app-1.0.jar" with the name of YOUR jar file.

```
java -jar build/libs/build-tools-exercises-1.0-SNAPSHOT.jar
```


EXERCISE 5: Start App with 2 Parameters

Now you want to add parameters to your application, so you and other users can pass different values on startup.

- Add parameter input to the Java code (see code snippet below, which you can copy)*
- Rebuild the jar file
- Execute the jar file again with 2 params
```
# Code snippet for Exercise 5!
# Code snippet to add inside Application.java on line 16

Logger log = LoggerFactory.getLogger(Application.class);
try {
      String one = args[0];
      String two = args[1];
      log.info("Application will start with the parameters {} and {}", one, two);
} catch (Exception e) {
      log.info("No parameters provided");
}

```
