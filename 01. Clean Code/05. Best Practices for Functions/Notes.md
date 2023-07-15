# Function Best Practices

**1) Function must be small and do only one thing:**<br/>
A function should have a clear and specific purpose, performing a single task or operation. Breaking down complex functionalities into smaller functions improves code readability, maintainability, and testability. It also promotes code reuse and modularity. Here's an example:

```java
// Example: A function to calculate the square of a number
public int calculateSquare(int number) {
    return number * number;
}
```
In this example, the `calculateSquare()` function has a single responsibility: calculating the square of a given number. By focusing on a specific task, the function is easier to understand and maintain.

**2) It must have descriptive naming:**<br/>
Descriptive naming is crucial for functions as it reveals the intention behind the code. Using descriptive names helps other developers understand the purpose of the function without needing to dive into its implementation details. Following a verb-noun or verb-noun-noun pattern, where the verb represents the action and the noun represents the subject, makes the function's purpose clear and explicit. Here's an example:

```java
// Example: A function to find the maximum value between two nodes
public int findMax(Node parent, Node child) {
    // implementation logic
    // ...
    return max;
}
```
In this example, the function name `findMax` clearly indicates its purpose: finding the maximum value between two nodes. The names `parent` and `child` provide context for the inputs, further enhancing code readability.

**3) Uniformness should be maintained:**<br/>
Maintaining uniform naming conventions for functions with similar purposes or operations enhances code consistency and readability. When multiple functions are performing similar actions, such as retrieving data, it's important to use consistent names that reflect their common purpose. This promotes a clear and understandable codebase. Here's an example:

```java
// Example: Functions for retrieving data with uniform naming
public String getData() {
    // retrieve data logic
    // ...
    return data;
}

public int getMarks() {
    // retrieve marks logic
    // ...
    return marks;
}

public String getUserName() {
    // retrieve username logic
    // ...
    return username;
}
```
In this example, the functions `getData()`, `getMarks()`, and `getUserName()` follow a consistent naming convention for retrieving different types of data. This uniformity improves code readability, making it easier to understand and work with the functions.

**4) Avoid unnecessary length of function:**<br/>
Functions should be concise and focused, with names that convey their purpose clearly. Avoid unnecessarily long function names unless there is a specific reason for the additional detail. By using succinct and meaningful names, the function's purpose is effectively communicated without excessive length. Here's an example:

```java
// Example: A function to check if a number is prime
public boolean isPrime(int number) {
    // check if the number is prime logic
    // ...
    return isPrime;
}
```
In this example, the function name `isPrime()` effectively conveys the purpose of checking whether a given number is prime. Using a concise and descriptive name reduces unnecessary length while still capturing the meaning of the function.


**5) Setters should be void:**<br/>
Setters are functions used to update the state of an object. It is a best practice for setters to have a return type of `void` instead of returning a value. Setters are primarily responsible for modifying the object's internal state, and it is not necessary to return anything since the state change itself is the desired outcome. Here's an example:

```java
// Example: A setter method for updating a value
public void updateVal(int i) {
    // update the value
    // ...
}
```
In this example, the `updateVal()` method updates a value but does not return any value. By making the setter void, it aligns with the convention of setters not returning any specific value.

**6) Avoid if conditions:**<br/>
Avoiding excessive `if` conditions improves code readability and maintainability. Instead of using conditional statements, it is often preferable to use separate functions or methods to handle different cases or conditions. By splitting the logic into separate functions, you can eliminate complex branching and make the code more modular. Here's an example:

```java
// Example: Processing orders based on COVID essential status
void processOrder(int id, boolean isCovidEssential) {
    if (isCovidEssential) {
        // process COVID essential order logic
        // ...
    } else {
        // process general order logic
        // ...
    }
}
```
In this example, the original code uses an `if` condition to differentiate between processing COVID essential orders and general orders. By refactoring the code, we can have separate functions for each type of order to avoid the `if` condition:

```java
// Refactored Example: Separate functions for processing COVID essential and general orders
void processCovidEssentialOrder(int id) {
    // process COVID essential order logic
    // ...
}

void processGeneralOrder(int id) {
    // process general order logic
    // ...
}
```
By using separate functions, we eliminate the need for the `if` condition, making the code clearer and more focused on the specific task at hand.

**7) You should not have more than 2 levels of indentation:**<br/>
Excessive indentation levels in a function can indicate complex logic or nested structures, which can make the code harder to read and understand. Limiting the indentation to two levels helps keep the code more manageable and improves readability. Here's an example:

```java
// Example: Limiting indentation levels in a function
public void processItems(List<Item> items) {
    for (Item item : items) {
        if (item.isValid()) {
            // process valid item
            // ...
        } else {
            // handle invalid item
            // ...
        }
    }
}
```
In this example, the function `processItems()` has a maximum of two levels of indentation, making the code easier to read and comprehend.

**8) We should be passing fewer arguments as much as possible:**<br/>
Passing a large number of arguments to a function can make the code more complex, less readable, and harder to test. It is considered a best practice to minimize the number of arguments passed to a function, ideally keeping it below or equal to three. If a function requires multiple inputs, consider encapsulating related arguments within a single object or using data structures to group the inputs. This improves code clarity and reduces the cognitive load when working with the function.

**9) Use separate functions for handling external resources:**<br/>
When dealing with external resources, such as files or databases, it is a good practice to encapsulate the resource-related operations in separate functions. This promotes modularity and separation of concerns. By having dedicated functions for opening, reading, and closing resources, you ensure that the primary function is focused on its core functionality, without worrying about resource management. Here's an example:

```java
// Example: Reading data from a file using separate resource functions
public Marks getMarks() {
    String dataFromFile = readFromFile(...);
    // ...
    // process the data
    // ...
    return marks;
}

private String readFromFile(...) {
    openFile(...);
    String data = readFile(...);
    closeFile(...);
    return data;
}
```
In this example, the `getMarks()` function calls the `readFromFile()` function to handle reading data from a file. By separating the resource-related operations, the primary function remains focused on processing the data without the burden of managing the file.

**11) A function should not have both write and read responsibilities:**<br/>
To improve code readability and maintainability, it is recommended to separate the responsibilities of writing and reading within functions. A function should focus on either modifying the state of an object or retrieving information, but not both. By adhering to this principle, functions become more modular, testable, and easier to understand.

**12) DRY (Do Not Repeat Yourself):**<br/>
The DRY principle advocates for avoiding code duplication by promoting code reuse and modularity. If you find duplicate code or similar logic in multiple places, it is best to extract that logic into a separate function or module and reuse it. This reduces code redundancy, improves maintainability, and ensures consistency across the codebase.

