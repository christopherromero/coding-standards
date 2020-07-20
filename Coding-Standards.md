# Coding Standards

Table of Contents

- [1. Naming Conventions](#1-naming-conventions)
- [2. Comments and General Style Guidelines](#2-comments-and-general-style-guidelines)
- [3. General Standards and Practices](#3-coding-standards-and-practices)
- [4. Testing](#4-testing)
- [5. Pull Requests](#5-pull-requests)
- [6. Databases](#6-databases)
- [7. APIs](#7-apis)
- [8. Plugins and Consumers](#8-plugins-and-consumers)

## 1. Naming Conventions

### 1.1 Capitalization Styles

Use the following three conventions for capitalizing identifiers.

- **Pascal case** – The first letter in the identifier and the first letter of each subsequent concatenated word are capitalized. You can use Pascal case for identifiers of three or more characters. E.g.: BackColor
- **Camel case** – The first letter of an identifier is lowercase and the first letter of each  subsequent concatenated word is capitalized. E.g.: backColor
- **Uppercase** – All letters in the identifier are capitalized. Use this convention only for identifiers that consist of two or fewer letters. E.g.: System.IO, System.Web.UI

### 1.2 Capitalization Rules

| Identifier                   | Case   | Rules                                                                                                                                                                                                                                                                                                                                                | Example                                                       |
| ---------------------------- | ------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------- |
| Attribute                    | Pascal | Add the suffix Attribute to custom attribute classes                                                                                                                                                                                                                                                                                                 | ObsoleteAttribute{}                                           |
| Arrays                       | Pascal | For variables that hold a reference to an array, list or other collection, use a plural noun                                                                                                                                                                                                                                                         | Customers, financialRecords.                                  |
| Backend API                  | Pascal | Use the pattern Execution.[Functionality].Api                                                                                                                                                                                                                                                                                                        | Execution.Shipment.Api,Execution.ShipmentTracking.Api         |
| Class                        | Pascal | Use a noun or noun phrase to name a class Where appropriate, use a compound word to name a derived class. The second part of the derived class's name should be the name of the base class. E.g.: ApplicationException is an appropriate name for a class derived from a class named Exception, because ApplicationException is a kind of Exception. | AppDomain                                                     |
| Class-scoped variable        | Camel  |                                                                                                                                                                                                                                                                                                                                                      | _someVariable                                                 |
| Enum type                    | Pascal |                                                                                                                                                                                                                                                                                                                                                      | ErrorLevelEnum                                                |
| Enum values                  | Pascal |                                                                                                                                                                                                                                                                                                                                                      | FatalError                                                    |
| Event                        | Pascal |                                                                                                                                                                                                                                                                                                                                                      | ValueChange                                                   |
| Exception class              | Pascal | Always ends with the suffix Exception                                                                                                                                                                                                                                                                                                                | WebException                                                  |
| Function or method parameter | Camel  | Use descriptive parameter names. Parameter names should be descriptive enough that the name of the parameter and its type can be used to determine its meaning in most scenarios.                                                                                                                                                                    | typeName                                                      |
| Gateway API                  | Pascal | Use the pattern [UI/Plugin name].Api                                                                                                                                                                                                                                                                                                                 | Execution.ShipmentSearch.UI.ApiExecution.ShipmentTracking.Api |
| Interface                    | Pascal | Name interfaces with nouns or noun phrases, or adjectives that describe behaviour. For example: The interface name IComponent uses a descriptive noun The interface name ICustomAttributeProvider uses a noun phrase The name IPersistable uses an adjective Prefix interface names with the letter I to indicate that the type is an interface.     | IDisposable                                                   |
| Namespace                    | Pascal | Use directories to group the classes and use namespace to reflect parent                                                                                                                                                                                                                                                                             | System.IO                                                     |
| Plugin/consumer              | Pascal | Use the pattern Execution.[Functionality].Plugin/Consumer Use the suffix Consumer for Kafka Use the suffix Plugin for Enterprise Service Bus (ESB)                                                                                                                                                                                                   | Execution.LoadEvents.Plugin                                   |
| Public property              | Pascal |                                                                                                                                                                                                                                                                                                                                                      | BackColor                                                     |
| Public or internal method    | Pascal | Use verbs or verb phrases to name methods                                                                                                                                                                                                                                                                                                            | ToString                                                      |
| Private or protected method  | Pascal | Use verbs or verb phrases to name methods.                                                                                                                                                                                                                                                                                                           | calculatedValues                                              |
| Read-only Static field       | Pascal |                                                                                                                                                                                                                                                                                                                                                      | RedValue                                                      |
| UI                           | Pascal | Use pattern Execution.[Functionality].UI                                                                                                                                                                                                                                                                                                             | Execution.ShipmentSearch.UI                                   |
| Async methods                | Pascal | Use verbs or verb phrases to name methods and append the suffix "Async"                                                                                                                                                                                                                                                                              | AddMessageAsync                                               |

### 1.3 Case Sensitivity

Do not create a function with parameter names that differ only by case. E.g.:

```c#
{
    void MyFunction(string a, string A)
}
```

Do not create a namespace with type names that differ only by case. E.g.:

```c#
{
    System.Windows.Forms.Point;
    pSystem.Windows.Forms.POINT p;
}
```

Do not create a type with property names that differ only by case. E.g.:

```c#
{
    int Color {get, set}
    int COLOR {get, set}
}
```

Do not create a class with method names that differ only by case. E.g.:

```c#
{
    void calculate();
    void Calculate();
}
```

### 1.4 Meaningful Names - Recording Intention

Member and variable names should be carefully chosen to convey as much information as possible about their function and usage.

- Do use vague descriptive nouns and verbs that record what action will be taken by functions and methods and what data they act upon. E.g.: calculateAverages, createCustomer, clearTotalFields.

- Do not use names that simply describe the structure of that data rather than its purpose. E.g.: kvDict, dictionary, integerList

- Do not use variable names with a ‘the’ prefix. E.g.: theCustomer

- Avoid using numbers in names unless, rather describe how a set of variables differ.

- Avoid naming a variable the same name as the type

When two or more variables of the same type are in use in the same general area, make sure they are named in a way that differentiates them in an informative way.

Bad Practice:

```c#
{
    customer1.Save();
    customer2.Save();
}
```

Good Practice:

```c#
{
    oldCustomer.Save();
    newCustomer.Save();
}
```

When naming an identifier the name should be descriptive yet concise. Each identifier should have a name that tells the reader exactly what the identifier is or does. Avoid vague names that are single characters or include numbers.

### 1.5 Abbreviations

Follow these rules regarding the use of abbreviations:

- Where possible, do not use abbreviations or contractions as parts of identifier names.
  - For example, use GetWindow instead of GetWin.

- Where appropriate, use well-known acronyms to replace lengthy phrase names. For example, use UI for User Interface and OLAP for On-line Analytical Processing

- When using acronyms, use Pascal case for acronyms more than two characters long. For example, use HtmlButton. However, you should capitalize acronyms that consist of only two characters, such as System.IO instead of System.Io. Avoid removing vowels from abbreviations. 

## 2. Comments and General Style Guidelines

Well written commentary allows for readers and other developers to easily scan code and derive a basic understanding of process flow, or to easily find each section of code that performs a task, without necessarily reading each and every line.

Writing good commentary also forces the author to think about how their code works at a higher level and in the larger context of the application.

The ability of a developer to quickly and accurately read code is aided (or impeded) by the quality of the commentary and arrangement of the lines of code it relates to. Code that is well commented in clear and concise and separated logically into vertical blocks, makes code reading easier.

Consider the following code example:

```c#
{
    // Setup the initial properties for the customer and validate them
    var customer = new Customer();
    customer.SetBalance(0);
    customer.Name = "Joe";
    customer.Address = "123 Martin Luther King Jr Way";
    customer.Validate();

    // We must save the customer before we can return its identity
    var myRepo = Framework.GetInstance;
    ICustomerRepository;();
    int newId = myRepo.Save(customer);
    return newId;
}
```

By logically using vertical space and some detailed yet concise comments, the developer has noted useful information to the reader. Code should be an expression *of what* a control flow does *and* how it does it, but it rarely *records why*. Comments record the intention of the developer for future reference. Keep in mind, that code that seems extraneous or unusual to the reader may be required to operate in a specific way because of some external dependencies that are not readily apparent unless referenced in a comment.

### 2.1 XML Commenting

The minimum standard for XML comments is:

- Classes must always have a &lt;summary&gt; tag.

- Private methods in a class must have a &lt;summary&gt; tag.

- Public methods must have complete XML documentation, including tags for a summary, return value, and any generic types.

- Internal methods, classes and other types must have a &lt;summary&gt; tag.

- A tag must never be empty. If an auto-generated tag is not used according to the above rules, it should be deleted.

### 2.2 Commenting -- Before vs. After

Comments should generally come before a line or block of code to declare its intentions, not after or on the same line.

Good Practice:

```c#
{
 // Tell the user that something went wrongConsole.WriteLine($"An error occurred: {errMsg}");
}
```

Bad Practice:

```c#
{
    Console.WriteLine($"An error occurred: {errMsg}");
    // Tell the user that something went wrong
}
```

 ### 2.3 Comment Block

Developers should never use the /\* \*/ style of comments except to *temporarily* comment out a block of code during development. Use the // style instead.

Comment blocks are often used for permanently commenting out blocks of code that are no longer relevant. This code should be deleted. If required, it can be recovered from source control.

### 2.4 Code Blocks

Not every line of code requires a comment. Blocks of code that perform a common task (e.g.: populating an object) can be preceded by a line or two of comments. If a large body of code is simple enough that it doesn’t require any commentary at all, write a short comment before it summarizing its function, separated from the code by a single line of whitespace.

If statements should always use braces, even if there is only a single statement that results from

the condition evaluating to true.

Bad Practice:

```c#
{
    if (tmpCustomer.IsNew) tmpCustomer.Save();
    if (tmpCustomer.IsNew)tmpCustomer.Save();
}
```

Good Practice:

```c#
{
    if (tmpCustomer.IsNew)
    {
        tmpCustomer.Save();
    }
}
```

The exception to this rule is when an obvious shortcut can be taken to return from a method. There should be a single line of whitespace before and after that line:

```c#
{
    if (tmpCustomer.IsNew) return;
}
```

### 2.5 Code Blocks

Comments should follow a *narrative* style. The comments should describe the overall flow and logic of the code so that, if a developer were to read only the comments, they would still be able to get a fair idea of the how the code works and its control flow without needing to read the code itself.

### 2.6 Do Not Write Low-Content Comments

Avoid writing comments that simply describe what a reasonably competent developer could easily read in the code itself. E.g.:

```c#
{
    // Set the customer ID to 0
    customer.Id = 0
}
```

Instead, describe why an action is occurring, or write nothing at all:

```c#
{
    // The customer ID must initially be set to zero so that the
    // repository recognizes a the customer as new and creates
    // an appropriate record
    customer.Id = 0
}
```

### 2.7 TODO: and FIXME

Comments can include a TODO prefix to indicate low priority clean-up tasks or unimplemented features that don’t cause the code to deviate from requirements. For instance, if a section of code works but is overly complex, a comment with a TODO: prefix can be used to inform other developers that it is a good candidate for a re-write. Use a FIXME prefix to call attention to a comment describing code that is broken, deviates from requirements, may cause problems in the future or in some other way is not optional to fix. The presence of a FIXME prefix in a section of code should generally indicate that it is not yet ready for release, or that it must be fixed as a high priority.

Developers should configure their IDE to display tasks for FIXME tags by following these steps:

1. On the Tools menu, click Options

2. In the option tree view, click the Task List item under Environment.

3. Type FIXME in the name field

4. Set the priority to High

5. Click Add

Examples:

```c#
{
    // TODO: This works but there must be a more elegant way of doing it!
}
```

```c#
{
    // FIXME: Possible race condition! Issue # 12345
}
```

### 2.9 Spacing and Code Grouping

Use vertical white space to separate and group code into blocks of similar functionality or purpose.

- Use a single blank line before and after a code block such as an if, for or switch statement in order to make it stand out

- Use a single blank line before and after an important line of code that you need to draw attention to

- Use a single blank line before and after a block of code that has a common purpose, such as setting all the properties of a newly created object

- In general, use vertical whitespace to divide code into logical grouping of similar functionality. This allows developers or reviewers to quickly scan and understand the code

- Do not add blank lines between multiple close braces that terminate nested code blocks.

## 3 Coding Standards and Practices

### 3.1 Standard Class Structure

The members of a class should be organized according to a standard template in this order:

- Private class-scoped member variables

- Constructors

- Public properties

- Public methods

- Private methods

- Simple interface implementations, such as IComparable, etc.

The exception to this rule is when an interface implementation makes up the bulk of a class—for instance in repository implementations. In that case, the interface implementation does not need to be separated out.

### 3.2 Null-Conditional Operator

Use the null-conditional operator to protect against null values:

```c#
{
    // This will ensure an exception is not thrown if location is null,
    // and will set instead set locationName to nullstring
    locationName = locationName?.Name;
}
```

However, use this operator carefully. It should only be used when the resulting value is allowed to be null. For instance, if location is null, it is actually better to throw a null reference exception when the location variable is accessed than further down the code path when the locationName variable is used:

```c#
{
    string locationName = myLocation?.Name;
    // This code might be several thousand lines away and will cause a
    // null reference exception if the original customer object was
    // nullString
    trimmedName = locationName.Trim();
}
```

### 3.3 Line Wrapping

Break up lines of code that are more than 120 characters in length and indent all subsequent lines that are part of the same statement.

Try to find a logical place in the line to place the break. Usually the best place is after an operator. Leave the operator trailing at the end of the wrapped line (as opposed to starting the next line) to give an immediate visual cue that the statement continues on the following line.

Example:

```c#
{
    Console.WriteLine("Customer " + customer.Name + " has a balance of"+
        customer.Balance.Dollars + " dollars and " +
        customer.Balance.Cents + " cents.");
}
```

After a comma in a method declaration:

```c#
{
    private int getInternal(IParticipantReadContext readContext,
        ReadSpecification querySpec, Plan referencePlan)
}
```

Before a member accessor:

```c#
{
 string customerName = customers[myCustomerNumber].PersonalInfo.
    NameInfo.FirstName.Trim()
}
```

### 3.5 Using Parentheses

Use parentheses defensively. to make operator order obvious and to clarify the intent of a calculation.

```c#
{
    // Both of these lines produce the same result, but the second line is more explicit
    if (foo == 3 * 7 + 4 && bar != 0)

    if ((foo == ((3 * 7) + 4)) && (bar!= 0))
}
```

### 3.4 Variable Definitions

Variables should be defined as close as possible to their actual usage– avoid a large block of definitions at the top of a class or method.

### 3.5 Exception Handling

Exceptions should only be thrown in *exceptional* circumstances. Don’t use an exception to return feedback to calling code about the normal operation of method. An exception should only be thrown if a method is unable to complete its work – the exception then indicates that processing failed completely.

The basic rule of exception handling is, generally speaking, don’t handle exceptions. Exceptions should only be caught in the following circumstances:

- The code can actually do something to correct the problem. For instance, a timeout exception can be handled by retrying an operation.

- The exception must be hidden because it may contain sensitive information that should not be shared with a caller. For instance, a web service should not return detailed information about the database error that caused an operation to fail

- The exception has a different meaning outside of the library of class where it occurred. For instance a primary key violation in database code might indicate that a caller is attempting to add an entity that already exists in the database

### 3.6 Property Guidelines

Use a method instead of a property when:

- The operation is a conversion (such as Object.ToString()) as the complexities can quickly add up and clear organization is key for future readers

- Obtaining a property value using the Get accessor on an object modifies the state of the object

- Calling the member twice in succession results in different results

Use a property getter for quick retrievals that do not involve complex side effects. For instance,

code to retrieve the next N bytes from a stream should be accessed through a method because it

has an observable side effect (i.e.: the position of the reader in the stream is updated).

### 3.7 Constructors

Some rules for constructors:

- If a class should not be publicly creatable, specify a private default constructor

  - By default, all classes should have private or internal constructors. Only classes that are explicitly intended for use outside the assembly should have public constructors and public visibility

- Make proper use of protected and internal constructors

  - Use an internal constructor when a caller outside the assembly should not be able to create a new instance of a class.

  - Use a protected constructor when only derived classes should be able to create an instance of the base class

  - Generally, a constructor should contain parameters that setup the class in a valid state. For instance, if a Customer class is invalid without an Address object, the constructor must contain an Address parameter (these are referred to as the invariants of the class).

    An exception to this rule is for when a constructor can setup default state that makes the class valid. For instance, a Point2d class might take X and Y coordinates as arguments in its constructor, but a default parameter-less constructor could just set these values to 0 by default.

- For classes with overloaded constructors, be consistent with the argument order

### 3.8 Returning Arrays and Collections

Members that return arrays or collections should (generally) never return null. Always prefer to return an empty collection or zero-length array, unless a null result has some special significance.

### 3.9 Code for Clarity, Not Compactness

Developers should place an emphasis on readability. Code should be readable and should favor clarity over compactness. Avoid excessive use of syntactical ‘tricks’ or short-hand.

While useful, Bad Practice:

```c#
{
    int nValue = (User != null) ?
        ((User.Active) ? User.Value1 : User.Value2) : 0;
}
```

Good Practice:

```c#
{
    int nValue = 0;
    if (User != null)
    {
        if (true == User.Active)
        {
            nValue = User.Value1;
        }
        else
        {
            nValue = User.Value2;
        }
    }

        // Or a reasonable common ground between
        // readability and compactness:
        if (User != null)
        {
            nValue = User.Active ? User.Value1 : User.Value2;
        }
}
```

### 3.10 Avoid Excessive Vertical Whitespace

Although these style guidelines make frequent recommendations to use vertical whitespace, two

blank lines should never appear consecutively in a source file.

It is recommended to include a single blank line at the start of a class.

### 3.11 Using Regions

Use code outlining to group the code in your source file in logical units that can be collapsed or

expanded to improve readability.

Examples of good units for grouping include:

- Private ‘utility’ functions

- Interface implementations

- Generated code

When possible, group members by business function. For example:

- Reading and writing data

- Validation logic

Do not use outline regions to group code by visibility or scope, such as private methods, public methods, constructors, etc.

Structure your outlined regions so that, when closed, they are separated by a single blank line:

{Insert code snippet}

### 3.12 Removing Unused Code

Unreachable or unused code should be removed, unless there is a clear requirement for it to be

used in the near future. Do not comment out large blocks of code when they are no longer

required—instead, delete the unused code.

## 4. Testing

- **All major test cases should be implemented as unit and/or AATs** -- make sure to test both happy and unhappy code paths. Tests are the only way you have to ensure that your code continues to work in prod after you're done with your project!
- Naming: class name + method name should read like a sentence
  - Class: `[Name of class under test]Should` (ex., ConfigurationRepositoryShould)
  - Methods: `[What_the_method_is_testing]` (ex., Get_connectionString_from_config)

## 5. Pull Requests

- Ensure your code is not introducing new criticals or blockers 
- Ensure code complexity for functions is < 10 for your code 
- Ensure code duplication did not go up
- Ensure maintainability rating did not go up
- Ensure everything added to .config got added to .token file, as well 
- Ensure new tokens are in Octopus Deploy prior to submitting the PR for review
- First level of approval needs to be done by the Execution Advocates on your team (if you have any) or another developer on your team (if you don't)
- Once the PR has been approved by Advocate/developer, assign the PR to the `Execution-Gatekeepers` team
- **SLA for reviews is 2 days** after the PR has been marked as ready for the Execution team

## 6. Databases

- All (new) database objects related to a DevOps product should be in a schema specific to that product
- Naming conventions 
  - Tables: plural (ex., Loads not Load)
  - Stored procedures: `[TableName (singular)]_[Action]` (ex., Load_Get or Load_GetByEmployee)
- UDTs: only use them for simple structures (1-2 columns)
- Avoid business logic in stored procedures 

## 7. APIs

### 7.1 Routes: Name and Operation Conventions

| Resource            | GET                                                                                                                                   | POST                  | PUT                                                                  | DELETE                                                     |
| ------------------- | ------------------------------------------------------------------------------------------------------------------------------------- | --------------------- | -------------------------------------------------------------------- | ---------------------------------------------------------- |
| /customers          | Retrieve all customers                                                                                                                | Create a new customer | Bulk update of customers (if implemented), otherwise return 404      | Remove all customers (if implemented) otherwise return 404 |
| /customers/1        | Retrieve the details for customer with ID 1.  If customer doesn’t exist, return 404.                                                  | Return 404            | Update the details of customer 1 if it exists, otherwise return 404. | Remove customer 1.  If customer doesn’t exist, return 404. |
| /customers/1/orders | Retrieve all orders for customer 1.  If customer doesn’t exist, return 404. If customer doesn’t have orders, then return empty array. | Return 404            | Return 404                                                           | Return 404                                                 |

### 7.2  Filtering/Sorting/Paging

| Resource                                      | GET                                                                                            | POST       | PUT        | DELETE     |
| --------------------------------------------- | ---------------------------------------------------------------------------------------------- | ---------- | ---------- | ---------- |
| /customers?firstName=Bob                      | Retrieve all customers with a first name of ‘Bob’.                                             | Return 404 | Return 404 | Return 404 |
| /customers?**sortBy**=firstName,desc;lastName | Retrieve all customers with ascending sort by first name.                                      | Return 404 | Return 404 | Return 404 |
| /customers?**pageSize**=25&**pageIndex**=5    | Retrieve 25 objects, offset by 5 pages of data.  So we’d be returning objects 101 through 125. | Return 404 | Return 404 | Return 404 |

## 7.3  Routes: Guidelines

- All routes should be nouns (objects) and not verbs (actions).
- Routes should be plural
- Routes should be "hackable" - meaning that you should be able to delete part of the route and get back objects you would expect.  (ex.,  if you have route ```/employees/2343/shipments/11992```, you would expect that you could get back the object for employee with ID of 2343 if you delete off the "shipments" part of this route)
- Following a given resource (e.g. "orders", "shipments", etc.), the next piece of the route should be the unique ID for *individual* objects.
  
   | Bad Routes              | Proper Routes                                                  |
   | ----------------------- | -------------------------------------------------------------- |
   | ``` /getcustomers ```   | ``` /customers ```                                             |
   | ``` /updatecustomer ``` | ``` /customers ``` [Perform PUT]                               |
   | ``` /order ```          | ``` /orders ```                                                |
   | ``` /employeebyname ``` | ``` /employees?firstName=bob ```                               |
   | ``` /convert2pdf ```    | ``` /documentConversions ``` [Send POST to perform the action] |

- For pagination, we will use `pageSize` and `pageIndex` keywords.
- For filtering:
  - Just use the name of the field (e.g. “firstname”).  Do not add “filter” to the query string key name.
  - If you have exceptional cases where your filtering criteria are complex and/or larger amounts of data, instead of using the GET method and query strings, you may use POST while placing filter criteria in the body of the request.
- For sorting:
  - Use `sortBy` for keyword, set to the name of the field to search by.
  - If the user wants to specify ascending or descending order, they will add a comma after the field name that they are sorting by, and then specifying “desc” if they want descending, and put nothing if they want ascending (e.g. ascending will be the default convention when nothing is specified).
- Put all route definitions in a Routes.cs file within the <Api>.ServiceModel project.
  - This will help anyone to very quickly review the route design for a given API.
  - This will also help enforce consistency among the routes by putting them all right next to each other.
  - [See example here](https://github.chrobinson.com/GlobalForwarding/GF.Alerts.API/blob/development/src/GF.Alerts.API.ServiceModel/Messages/Routes.cs).

### 8 Plugins and Consumers

- Should not contain business logic
- Should pass through to gateway services (i.e., all plugins and consumers should have a gateway service that contains the logic needed to perform the functionality; they shouldn't call back-end services directly)