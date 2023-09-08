<details>
  <summary> Learning to test Spring Boot </summary>

### What is it for?

- Learn Important Concepts behind Test Driven Development 
- Understand different types of testing - Unit, Integration, Functional 
- Master the JUnit 5 Testing API 
- Easily integrate Mockito with JUnit 5 Tests 
- Migrate JUnit 4 tests to JUnit 5 
- Test Spring Framework Applications with JUnit 5 and Mockito 
- Write Unit Tests with Spring MVC Test 
- Learn to use testing features of Spring Boot

### Where is the course?

- [Udemy](https://www.udemy.com/course/testing-spring-boot-beginner-to-guru/)

---

<details> 
  <summary>Section 1 - Introduction </summary>

### About

-[x] Completed


- How to work with GitHub and compare my code with the instructor's code
- What IDE to use

---
</details>

<details> 
  <summary>Section 2 - Introduction to testing software </summary>

### About

-[x] Completed

### Why testing is great?

    1. No more fix this and break that
    2. Best practice in the industry
    3. Proves that your code is running correctly

### Types of tests

    1. Unit test (the majority of tests)
        Should be fast, specific and light
    2. Integration test
        Larger scope than unit test's, tests the overall behavior of the system
    3. Funcional test
        Application is tipically live, tests specific functional points

### TDD (test) x BDD (behavior)

    1. TDD => write tests firt, code to fix tests, refactor code 
    2. BDD => when something happens then this happens 
    Use both!!!

### Common testing frameworks for Java

    1. JUnit
    2. TestNG
    3. Spock
    4. Cucumber
    5. Mockito
    6. Spring MVC Test
    7. REST Assured
    8. Selenium

### Continuous Integration

    A development practice that requires developers to integrate code into a shared repository verified by an automated build detecting problems early for each contribution
    1. Jenkins
    2. Bamboo
    3. TravisCI

### Continuous Deployment

    Should happen after every commit automatically deploying build artifacts after CI tests

---
</details>

<details> 
  <summary>Section 3 - TDD by example </summary>

### About

-[x] Completed

> Some quotes of **Kent Beck**, one of the **Agile Manifesto** signers and one of the **JUnit** developers, also author
> of **Extreme Programming Explained** and **Test-Driven Development by Example**
>
> "I am not a great programmer, I am a good programmer with great habits"
>

> "If there are forms of testing, like stress and load testing, that finds defect after development is completed, bring
> them into the development cycle. Run them continuously and automatically"

### First approach to tests - TDD

    1. Create the test class
    2. Create a MVP for your code
    3. Make a test run with the MVP
    4. Gradually update the code to get the expected results
    or
    1. Write a test (how the code should work)
    2. Write the code and make it run
    3. Update the code

---
</details>

<details> 
  <summary> Section 4  - Getting Started with JUnit </summary>

### About

-[x] Completed

### JUnit Modules

    JUnit Platform - The foundation for launching tests
    JUnit Jupiter - Programmimg model for writing tests
    JUnit Vintage - Test engine

### JUnit dependecies in Maven

  ~~~xml

<properties>
    <junit-platform.version>5.3.1</junit-platform.version>
</properties>
  ~~~

  ~~~xml

<dependencies>
    <dependency>
        <groupId>org.junit.jupiter</groupId>
        <artifactId>junit-jupiter-api</artifactId>
        <version>${junit-platform.version}</version>
        <scope>test</scope>
    </dependency>
    <dependency>
        <groupId>org.junit.jupiter</groupId>
        <artifactId>junit-jupiter-engine</artifactId>
        <version>${junit-platform.version}</version>
        <scope>test</scope>
    </dependency>
</dependencies>
  ~~~

  ~~~xml

<build>
    <plugins>
        <plugin>
            <groupId>org.apache.maven.plugins</groupId>
            <artifactId>maven-compiler-plugin</artifactId>
            <version>3.8.0</version>
        </plugin>
        <plugin>
            <groupId>org.apache.maven.plugins</groupId>
            <artifactId>maven-surefire-plugin</artifactId>
            <version>2.22.0</version>
            <configuration>
                <argLine>
                    --illegal-access=permit
                </argLine>
            </configuration>
        </plugin>
        <plugin>
            <groupId>org.apache.maven.plugins</groupId>
            <artifactId>maven-failsafe-plugin</artifactId>
            <version>2.22.0</version>
            <configuration>
                <argLine>
                    --illegal-access=permit
                </argLine>
            </configuration>
        </plugin>
    </plugins>
</build>
  ~~~

| **Annotations**     | **What it is for**                  |
|---------------------|-------------------------------------|
| @Test               | Determine a method as a test method |
| @BeforeEach         | Run a method before each test       |
| @AfterEach          | Run a method after each test        |
| @BeforeAll          | Run a method before the tests       | -> has to be a static method
| @AfterAll           | Run a method after the tests        | -> has to be a static method
| @RepeatedTes(times) | Run a test x times                  |

### Running test from command line with maven

    1. Open the cmd
    2. Move to your directory
    3. Select the mvnw.cmd with two commands: clean and test

~~~shell
  mvnw.cmd clean test
~~~

---
</details>


<details> 
  <summary>Section 5 - Testing Java with JUnit 5 </summary>

### About

-[x] Completed

> Example of assertion:
>
> assertEquals(value: 2, value: 2, failure message: "Values do not match")
>
> In [JUnit](https://junit.org/junit5/docs/current/user-guide/) documentation there are others

- You can use lambda expressions as an if statement when the assertion results in false
    - assertEquals (2, 2, () -> "Values do not match")
- You can use nested assertions with multiples assertAll
  >     assertAll ("message",
  >
  >        ( ) -> assertAll ("message",
  >               ( ) -> assertEquals (value, value, "message"),
  >               ( ) -> assertEquals (value, value, "message"))
  >        ( ) -> assertAll ("message",
  >               ( ) -> assertEquals (value, value, "message"),
  >               ( ) -> assertEquals (value, value, "message"))
  >  
  >       ));
- You can also use some libraries of JUnit as AssertJ and Hamcrest to give some more options preset

---
</details>

<details> 
  <summary>Section 6 - Advanced JUnit testing</summary>

### About

-[x] Completed
- You can add tags to your test and create a cofiguration to only run test with that especifically tag
- You can create test interfaces and implement them onto the classes you would want to test
- You can inject dependecies to be able to see extra info
    - TestInfo
    - RepetitionInfo
- @ExtendWith allows you to extend JUnit extensions

---
</details>

<details> 
  <summary>Section 7  - Test Execution </summary>

### About

-[x] Completed
- Test coverage is a handy tool to find out how much of your code is being covered in tests

---
</details>

<details> 
  <summary>Section 8 - JUnit 4 to JUnit 5 migration </summary>

### About

-[x] Completed
- Annotations differences from JUnit 4 to JUnit 5

| JUnit 4      | JUnit 5     |
|--------------|-------------|
| @Before      | @BeforeAll  |
| @After       | @AfterAll   |
| @BeforeClass | @BeforeEach |
| @AfterClass  | @AfterEach  |
| @Catgory     | @Tag        |

---
</details>

<details> 
  <summary>  Section 9  - Getting started with Mockito </summary>

### About

-[x] Completed
- Mockito is important to have light and fast tests not importing and using real files

### Mockito dependencies in Maven (keep JUnit)

  ~~~xml

<dependencies>
    <dependency>
        <groupId>org.mockito</groupId>
        <artifactId>mockito-core</artifactId>
        <version>${mockito.version}</version>
        <scope>test</scope>
    </dependency>
    <dependency>
        <groupId>org.mockito</groupId>
        <artifactId>mockito-junit-jupiter</artifactId>
        <version>${mockito.version}</version>
        <scope>test</scope>
    </dependency>
</dependencies>
  ~~~

### Creating Mockito Mocks with annotations

~~~java

public class AnnotationMocksTest {
    @Mock
    Map<String, Object> mapMock;

    @BeforeEach
    void setUp() {
        MockitoAnnotations.initMocks(this);
    }
}
~~~

- `@ExtendWith(MockitoExtension.class)` is an annotation to extend a Mockito

---
</details>

<details> 
  <summary> Section 10  - Behavior Driven Mockito </summary>

### About

-[x] Completed
- BDD is more of conceptual way of how you test your code
    - Given → when → then

---
</details>

<details> 
  <summary> Section 11 - Advanced Mockito </summary>

### About

-[x] Completed

---
</details>

<details> 
  <summary>Section 12  - Testing with Spring Framework </summary>

### About

-[x] Completed

---
</details>

<details> 
  <summary> Section 13 - Spring Frameork Testing Context</summary>

### About
-[x] Completed


- ``@SpringJUnitConfig`` tells spring which configuration to use then you can set classes ``Config`` to be used as a context


- ``@Configuration`` tells spring that this class is a context configuration class


- ``@SpringJUnitConfig(classes = yourClass.TestConfig.class)`` tells spring to use an inner class configuration and it shoulg point to a ``@Configuration static class``


- ``@ActiveProviles("yourProfile")`` and ``@Profile`` to set up specific profiles to your test and isolate classes and interfaces that are not need and could impact the test result
---
</details>

<details>
  <summary> Section 14 - Spring MVC Test </summary>

### About:
-[x] Completed


---
</details>

<details>
  <summary> Section 15 - Introduction to Testing with Spring Boot </summary>

### About:
-[x] Completed


- ``@SpringBootTest`` enables spring context

---
</details>
<details>
  <summary> Section 16 - Spring MVC Rest Controller </summary>

### About:
-[ ] Completed
---
</details>
</details>