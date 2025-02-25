![logo_ironhack_blue 7](https://user-images.githubusercontent.com/23629340/40541063-a07a0a8a-601a-11e8-91b5-2f13e4e6b441.png)

# LAB Java | Maven

## Introduction

In this lab, you will build a multi-module Maven project that simulates processing order data stored in JSON format. You will use the Gson library to convert JSON data into Java objects, then apply business logic to process these orders. The goal is to practice advanced Maven configurations—including creating a parent POM and setting up child modules—while enhancing your skills in JSON manipulation and modular project design.

<br>

## Requirements

1. **Repository Setup:**

   - Fork this repo.
   - Clone this repo.
   - Add your instructor and the class graders as collaborators to your repository. If you are unsure who your class graders are, ask your instructor or refer to the day 1 slide deck.
   - In the repository, create a Java project and add the code for the following prompts.

2. **Project Structure:**
   - Create a Maven project with a **parent POM**.
   - Create at least **two child modules**:
     - **Order Data Module:** This module is responsible for handling JSON order data.
     - **Order Logic Module:** This module implements business logic (e.g., calculating order totals or filtering orders).

## Submission

Once you finish the assignment, submit a URL link to your repository or your pull request in the field below.

<br>

## Instructions

### 1. Set Up the Parent POM

- **Create a New Parent Project:**
  - Start by creating a new directory for your project. The main project should be named **solution-lab-2.02-maven**.
- **Configure the Parent POM:**
  - Create a `pom.xml` in your parent directory.
  - Include project metadata (groupId, artifactId, version) and set the packaging to `pom`.
  - Define a **properties section** (e.g., `java.version` and `project.build.sourceEncoding`).
  - Set up a **dependency management section** with at least one common dependency (for example, SLF4J).
  - Configure **repository** and **pluginRepository** sections to point to Maven Central.
  - List your child modules using a `<modules>` section (e.g., `order-data` and `order-logic`).

### 2. Create the Order Data Module

- **Module Setup:**

  - Within the parent project directory, create a new subdirectory named `order-data`.
  - Create a `pom.xml` for the module. Make sure this POM references the parent POM by including a `<parent>` section.

- **Implement JSON Processing:**
  - Develop a Java class (for example, `OrderProcessor.java`) that will:
    - Read a sample JSON string or file containing order details. Think about the fields you need, such as orderId, customer, items, and total.
    - Use the Gson library to convert the JSON data into Java objects. You should define classes like `Order` and `OrderItem` that map to the JSON structure.
    - Print the parsed order data to the console so you can verify that it’s being read correctly.

### 3. Create the Order Logic Module

- **Module Setup:**

  - In the parent project directory, create another subdirectory called `order-logic`.
  - Create a `pom.xml` for this module and reference the parent POM in its configuration.

- **Implement Business Logic:**
  - Develop a Java class (for example, `OrderCalculator.java`) that will:
    - Import the order model classes from the `order-data` module (remember to set up inter-module dependencies so that the classes are available).
    - Process the order data by applying business logic—such as calculating aggregate values (summing order totals, filtering orders based on certain criteria, etc.).
    - Print the results of the processing to the console.

### 4. Build the Multi-Module Project

- **Compile and Package:**
  - From your parent project directory, run the command:
    ```bash
    mvn clean install
    ```
  - This command should build the parent project and all child modules. Verify that the build completes successfully.

### 5. Testing and Verification

- **Run and Verify:**
  - Run the main method in your **Order Data Module** (e.g., in `OrderProcessor.java`) to check that the JSON data is being parsed correctly.
  - Run the main method in your **Order Logic Module** (e.g., in `OrderCalculator.java`) to ensure that your business logic processes the order data correctly.
  - Make sure the console outputs are clear and provide informative results.

<br>

## FAQs

<br>

<details>
  <summary style="font-size: 16px; cursor: pointer; outline: none; font-weight: bold;">I am stuck and don't know how to solve the problem or where to start. What should I do?</summary>

  <br>

If you are stuck in your code and don't know how to solve the problem or where to start, you should take a step back and try to form a clear, straight forward question about the specific issue you are facing. The process you will go through while trying to define this question, will help you narrow down the problem and come up with potential solutions.

For example, are you facing a problem because you don't understand the concept or are you receiving an error message that you don't know how to fix? It is usually helpful to try to state the problem as clearly as possible, including any error messages you are receiving. This can help you communicate the issue to others and potentially get help from classmates or online resources.

Once you have a clear understanding of the problem, you should be able to start working toward the solution.

</details>

<br>

<details>
  <summary style="font-size: 16px; cursor: pointer; outline: none; font-weight: bold;">How do I create a Maven project in IntelliJ?</summary>

  <br>

To create a Maven project in IntelliJ, you can follow these steps:

1. Open IntelliJ IDEA and click the "Create New Project" button.
2. In the "New Project" dialog, select "Maven" as the build system.
3. Specify the name of the project.
4. In the "Project Location" section, specify a location where you want to save your project.
5. Select the "Create Git repository" checkbox in order to initialize the git repository upon creation of the project.
6. Click the "Create" button to create the Maven project.

  <br>

</details>

<br>

<details>
  <summary style="font-size: 16px; cursor: pointer; outline: none; font-weight: bold;">What is a parent POM and why is it important?</summary>
  <br>
  A parent POM centralizes configurations (dependencies, plugins, properties) so that all child modules inherit them. This ensures consistency and simplifies maintenance across multi-module projects.

  <br>

</details>

<br>

<details>
  <summary style="font-size: 16px; cursor: pointer; outline: none; font-weight: bold;">How do I build a multi-module project using Maven?</summary>
  <br>
  Navigate to the parent project directory in your terminal and run `mvn clean install` to build the entire project. Maven will compile and package all modules as defined in the "modules" section of the parent POM.

  <br>

</details>

<br>

<details>
  <summary style="font-size: 16px; cursor: pointer; outline: none; font-weight: bold;">How do I set up inter-module dependencies in a multi-module project?</summary>
  <br>
  If one module needs to use classes from another module, you must add an inter-module dependency. In the dependent module's `pom.xml`, add a dependency with the groupId, artifactId, and version that match the module it depends on. For example, if your `order-logic` module needs to access classes from the `order-data` module, include the `order-data` module as a dependency. Make sure that the parent POM lists both modules and that you build the project using `mvn clean install` so that all modules are correctly compiled and packaged.

  <br>

</details>

<br>

<details>
  <summary style="font-size: 16px; cursor: pointer; outline: none; font-weight: bold;">I am unable to push changes to my repository. What should I do?</summary>

<br> <!-- ✅ -->

If you are unable to push changes to your repository, here are a few steps that you can follow:

1. Check your internet connection: Ensure that your internet connection is stable and working.
1. Verify your repository URL: Make sure that you are using the correct repository URL to push your changes.
1. Check Git credentials: Ensure that your Git credentials are up-to-date and correct. You can check your credentials using the following command:

```bash
git config --list
```

4. Update your local repository: Before pushing changes, make sure that your local repository is up-to-date with the remote repository. You can update your local repository using the following command:

```bash
git fetch origin
```

5. Check for conflicts: If there are any conflicts between your local repository and the remote repository, resolve them before pushing changes.
6. Push changes: Once you have resolved any conflicts and updated your local repository, you can try pushing changes again using the following command:

```bash
git push origin <branch_name>
```

</details>
