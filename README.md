## 💻 My Work

This project was completed as part of the **Accenture North America Software Engineering Virtual Experience** on Forage.

### 🎯 Objective
The goal was to complete the backend logic for the existing API endpoint:


The route and controller were already scaffolded, but the method body was left incomplete with a `TODO`.

---

### ✅ What I Implemented

I implemented the full logic inside the `SearchController.java` file to handle product searches based on a query string. My implementation supports:

- 🔍 **Case-insensitive partial search**  
  - Example: `query=choco` → matches names/descriptions like `"Chocolate Cake"`, `"milk chocolate bar"`  
  - Used `.toLowerCase().contains(...)`

- 🔐 **Exact match when query is in quotes**  
  - Example: `query="Chocolate Cake"` → only matches if the name or description is exactly `"Chocolate Cake"`  
  - Used `.equals(...)` for case-sensitive match (as per test expectation)

- 🛡️ **Null safety**  
  - Handled `null` names or descriptions to avoid `NullPointerException`  
  - Used safe checks like `name != null ? name.toLowerCase() : ""`

- 🧪 **Test-Driven Development (TDD)**  
  - I analyzed the failing Spock test specs
  - Designed logic to pass all 7 failing tests in `SearchControllerSpec.groovy`
  - Re-ran tests until full pass (✅)

---

### 📁 Files I worked in:
- `src/main/java/com/mockcompany/webapp/controller/SearchController.java`
- Verified functionality through: `src/test/groovy/com/mockcompany/webapp/controller/SearchControllerSpec.groovy`

---

### 📚 What I Learned:
- Implementing backend search logic using Java & Spring Boot
- How REST controllers work in Spring (`@RestController`, `@GetMapping`, `@RequestParam`)
- The difference between `.contains()`, `.equals()`, and `.equalsIgnoreCase()`
- How to safely handle user input and avoid common Java null issues
- Working with a real test suite (Spock/Groovy) and reading test-driven specs

---

### 🚀 Technologies used:
- Java 8
- Spring Boot
- JPA
- Gradle
- Groovy + Spock for unit testing

---

👩‍💻 Author: [Emilia Bravo](mailto:emiliabravo19@gmail.com)  




# Mock Company E-Commerce Application

This is the e-commerce application for Mock Company.  It's built using the following languages/frameworks

| Language/Framework       | Usage | Source Location |
| ------------------------ | ------- | --------------- |
| [Java 8][java]           | API Services Language                                                                            | [src/main/java][main]                                                       |
| [Gradle 6][gradle]       | Automation framework used for orchestrating the building/testing/packaging of the app            | [build.gradle]()                                                            |
| [Spring][spring]         | Framework for API development and dependency injection among other things                        | [src/main/java][main]                                                       |
| [JPA][jpa]               | Java Persistence API - Java framework for data access                                            | [ProductItem][ProductItem] / [ProductItemRepository][ProductItemRepository] |
| [Groovy 2.4][groovy]     | Language for Gradle build file and writing unit tests                                            | [src/test/groovy][test]                                                     |
| [Spock][spock]           | Framework for writing unit tests in Groovy                                                       | [src/test/groovy][test]                                                     |
| [Typescript][typescript] | Language for generating type safe javascript                                                     | [client-app/src][client-app]                                                |
| [React][react]           | Framework for building dynamic User Interfaces                                                   | [client-app/src][client-app]                                                |
| [Material UI][material]  | React library for building User Interfaces that meet the [Material Design Spec][material-design] | [client-app/src][client-app]                                                |


## Development Environment

To develop against this codebase, the following development tools should be installed on your
workstation first:
 * [Java 8 JDK](https://www.oracle.com/java/technologies/javase/javase-jdk8-downloads.html)
 * [Node 12+](https://nodejs.org/en/download/)
 * [Git](https://github.com/git-guides/install-git)   
 * [GitHub](https://docs.github.com/en/github/getting-started-with-github/quickstart/set-up-git)

### IDE Setup

You can use your IDE of choice to develop in this app but it should have Java/Gradle support at
a minimum.  The best recommendation for IDE is [IntelliJ Community Edition](https://www.jetbrains.com/idea/download/) as
it's free and works very well with Java/Gradle/Spring/Groovy/Spock.

## Getting Started

All build/test commands are to be run through a terminal using the [Gradle Wrapper](https://docs.gradle.org/current/userguide/gradle_wrapper.html) file.
This means, instead of each developer having to download and install the exact version of Gradle for the project,
there are shell scripts: [gradlew]() for posix (Mac/Linux) and [gradlew.bat]() for Windows. These shell scripts should be
used to execute any 'task', such as a `build`, `assemble`, or `test`.

For example, on Windows, to run all unit tests you would run: `gradlew test` and on Mac: `./gradlew test` from the root of the repository
where the gradlew files are located. On Windows, the `.bat` isn't needed because it automatically looks in the current working directory.  Where on Mac/Linux,
the developer has to use `./` at the beginning to indicate the script to run in the current working directory, indicated by the `.`

### Running the Application

To build and start the application, run the Gradle `bootRun` task

    ./gradlew bootRun  # on Mac/Linux
    gradlew bootRun    # on Windows

This will build the UI, build the Java API, and start the application at the following 
web address: http://localhost:8080

### Common Gradle Tasks

 * `test` - run all unit tests
 * `assemble` - build and package the application
 * `build` - runs `test` and `assemble`
 * `clean` - removes generated files/folders
 * `bootRun` - compiles and runs the application

[java]: https://docs.oracle.com/javase/8/docs/api/
[gradle]: https://docs.gradle.org/6.8.1/userguide/userguide.html
[main]: ./src/main/java
[jpa]: https://www.tutorialspoint.com/jpa/index.htm
[ProductItem]: ./src/main/java/com/mockcompany/webapp/model/ProductItem.java
[ProductItemRepository]: ./src/main/java/com/mockcompany/webapp/data/ProductItemRepository.java
[test]: ./src/test/groovy
[spring]: https://spring.io/projects/spring-framework
[groovy]: https://groovy-lang.org/
[spock]: https://spockframework.org/spock/docs/2.0/index.html
[typescript]: https://www.typescriptlang.org/docs/handbook/intro.html
[client-app]: ./client-app/src
[material]: https://material-ui.com/
[material-design]: https://material.io/
