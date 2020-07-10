Development Guide

1\. Naming Conventions

<u>1.1 Capitalization Styles</u>

Use the following three conventions for capitalizing identifiers.

> **Pascal case** – The first letter in the identifier and the first letter of each subsequent
>
> concatenated word are capitalized. You can use Pascal case for identifiers of three or more
>
> characters. E.g.: BackColor
>
> **Camel case** – The first letter of an identifier is lowercase and the first letter of each
>
> subsequent concatenated word is capitalized. E.g.: backColor
>
> **Uppercase** – All letters in the identifier are capitalized. Use this convention only for
>
> identifiers that consist of two or fewer letters. E.g.: System.IO, System.Web.UI
>
>  

<u>1.2 Capitalization Rules</u>

<table><thead><tr class="header"><th><strong>Identifier</strong></th><th><strong>Case</strong></th><th><strong>Rules</strong></th><th><strong>Example</strong></th></tr></thead><tbody><tr class="odd"><td>Attribute</td><td>Pascal</td><td><ul class="incremental"><li><blockquote><p>Add the suffix Attribute to custom attribute classes</p></blockquote></li></ul></td><td>ObsoleteAttribute{}</td></tr><tr class="even"><td>Arrays</td><td>Pascal</td><td><ul class="incremental"><li><blockquote><p>For variables that hold a reference to an array, list or other collection, use a plural noun</p></blockquote></li></ul></td><td>Customers, financialRecords.</td></tr><tr class="odd"><td>Backend API</td><td>Pascal</td><td><ul class="incremental"><li><blockquote><p>Use the pattern Execution.[Functionality].Api</p></blockquote></li></ul></td><td><p>Execution.Shipment.Api,</p><p>Execution.ShipmentTracking.Api</p></td></tr><tr class="even"><td>Class</td><td>Pascal</td><td><ul class="incremental"><li><blockquote><p>Use a noun or noun phrase to name a class</p></blockquote></li><li><blockquote><p>Where appropriate, use a compound word to name a derived class. The second part of the derived class's name should be the name of the base class.</p></blockquote></li></ul><blockquote><p>E.g.: ApplicationException is an appropriate name for a class derived from a class named Exception, because ApplicationException is a kind of Exception.</p></blockquote></td><td>AppDomain</td></tr><tr class="odd"><td>Class-scoped variable</td><td>Camel</td><td><ul class="incremental"><li><blockquote><p>Note: always use an underscore (_) prefix for class-scoped variables</p></blockquote></li></ul></td><td>_someVariable</td></tr><tr class="even"><td>Enum type</td><td>Pascal</td><td> </td><td>ErrorLevelEnum</td></tr><tr class="odd"><td>Enum values</td><td>Pascal</td><td> </td><td>FatalError</td></tr><tr class="even"><td>Event</td><td>Pascal</td><td> </td><td>ValueChange</td></tr><tr class="odd"><td>Exception class</td><td>Pascal</td><td><ul class="incremental"><li><blockquote><p>Always ends with the suffix Exception</p></blockquote></li></ul></td><td>WebException</td></tr><tr class="even"><td>Function or method parameter</td><td>Camel</td><td><ul class="incremental"><li><blockquote><p>Use descriptive parameter names. Parameter names should be descriptive enough that the name of the parameter and its type can be used to determine its meaning in most scenarios.</p></blockquote></li></ul></td><td>typeName</td></tr><tr class="odd"><td>Gateway API</td><td>Pascal</td><td><ul class="incremental"><li><blockquote><p>Use the pattern [UI/Plugin name].Api</p></blockquote></li></ul></td><td><p>Execution.ShipmentSearch.UI.Api</p><p>Execution.ShipmentTracking.Api</p></td></tr><tr class="even"><td>Interface</td><td>Pascal</td><td><ul class="incremental"><li><blockquote><p>Name interfaces with nouns or noun phrases, or adjectives that describe behaviour. For example:</p></blockquote><ul class="incremental"><li><blockquote><p>The interface name IComponent uses a</p></blockquote></li></ul></li></ul><blockquote><p>descriptive noun</p></blockquote><ul class="incremental"><li><blockquote><p>The interface name ICustomAttributeProvider uses a noun phrase</p></blockquote></li><li><blockquote><p>The name IPersistable uses an adjective</p></blockquote></li><li><blockquote><p>Prefix interface names with the letter I to indicate that the type is an interface.</p></blockquote></li></ul></td><td>IDisposable</td></tr><tr class="odd"><td>Namespace</td><td>Pascal</td><td> </td><td>System.IO</td></tr><tr class="even"><td>Plugin/consumer</td><td>Pascal</td><td><ul class="incremental"><li><blockquote><p>Use the pattern Execution.[Functionality].Plugin/Consumer</p></blockquote></li><li><blockquote><p>Use the suffix Consumer for Kafka</p></blockquote></li><li><blockquote><p>Use the suffix Plugin for Enterprise Service Bus (ESB)</p></blockquote></li></ul></td><td>Execution.LoadEvents.Plugin</td></tr><tr class="odd"><td>Public property</td><td>Pascal</td><td> </td><td>BackColor</td></tr><tr class="even"><td>Public or internal method</td><td>Pascal</td><td><ul class="incremental"><li><blockquote><p>Use verbs or verb phrases to name methods</p></blockquote></li></ul></td><td>ToString</td></tr><tr class="odd"><td>Private or protected method</td><td>Camel</td><td><ul class="incremental"><li><blockquote><p>Use verbs or verb phrases to name methods.</p></blockquote></li></ul></td><td>calculatedValues</td></tr><tr class="even"><td>Read-only Static field</td><td>Pascal</td><td> </td><td>RedValue</td></tr><tr class="odd"><td>UI</td><td>Pascal</td><td><ul class="incremental"><li><blockquote><p>Use pattern Execution.[Functionality].UI</p></blockquote></li></ul></td><td>Execution.ShipmentSearch.UI</td></tr></tbody></table>

 

<u>1.3 Case Sensitivity</u>

Do not create a function with parameter names that differ only by case. E.g.:

<table><tbody><tr class="odd"><td>void MyFunction(string a, string A)</td></tr></tbody></table>

Do not create a namespace with type names that differ only by case. E.g.:

<table><tbody><tr class="odd"><td><p>System.Windows.Forms.Point p</p><p>System.Windows.Forms.POINT p</p></td></tr></tbody></table>

Do not create a type with property names that differ only by case. E.g.:

<table><tbody><tr class="odd"><td><p>int Color {get, set}</p><p>int COLOR {get, set}</p></td></tr></tbody></table>

Do not create a class with method names that differ only by case. E.g.:

<table><tbody><tr class="odd"><td><p>void calculate()</p><p>void Calculate()</p></td></tr></tbody></table>

 

<u>1.4 Meaningful Names - Recording Intention</u>

Member and variable names should be carefully chosen to convey as much information as possible about their function and usage.

-   Do use vague descriptive nouns and verbs that record what action will be taken by functions and methods and what data they act upon. E.g.: calculateAverages, createCustomer, clearTotalFields.

-   Do not use names that simply describe the structure of that data rather than its purpose. E.g.: kvDict, dictionary, integerList

-   Do not use variable names with a ‘the’ prefix. E.g.: theCustomer

-   Avoid using numbers in names unless, rather describe how a set of variables differ.

 

When two or more variables of the same type are in use in the same general area, make sure they are named in a way that differentiates them in an informative way.

Bad Practice:

<table><tbody><tr class="odd"><td><p>customer1.Save();</p><p>customer2.Save();</p></td></tr></tbody></table>

 

Good Practice:

<table><tbody><tr class="odd"><td><p>oldCustomer.Save();</p><p>newCustomer.Save();</p></td></tr></tbody></table>

 

When naming an identifier the name should be descriptive yet concise. Each identifier should have a name that tells the reader exactly what the identifier is or does. Avoid vague names that are single characters or include numbers.

 

<u>1.5 Abbreviations</u>

Follow these rules regarding the use of abbreviations:

-   Where possible, do not use abbreviations or contractions as parts of identifier names.

> For example, use GetWindow instead of GetWin.

-   Where appropriate, use well-known acronyms to replace lengthy phrase names. For example, use UI for User Interface and OLAP for On-line Analytical Processing

-   When using acronyms, use Pascal case for acronyms more than two characters long. For example, use HtmlButton. However, you should capitalize acronyms that consist of only two characters, such as System.IO instead of System.Io.

 

2\. Comments and General Style Guidelines

Well written commentary allows for readers and other developers to easily scan code and derive a basic understanding of process flow, or to easily find each section of code that performs a task, without necessarily reading each and every line.

 

Writing good commentary also forces the author to think about how their code works at a higher level and in the larger context of the application.

 

The ability of a developer to quickly and accurately read code is aided (or impeded) by the quality of the commentary and arrangement of the lines of code it relates to. Code that is well commented in clear and concise and separated logically into vertical blocks, makes code reading easier.

 

Consider the following code example:

<table><tbody><tr class="odd"><td><p>// Setup the initial properties for the customer and validate them</p><p>var customer = new Customer();</p><p>customer.SetBalance(0);</p><p>customer.Name = "Joe";</p><p>customer.Address = "123 Martin Luther King Jr Way";</p><p>customer.Validate();</p><p> </p><p>// We must save the customer before we can return its identity</p><p>var myRepo = Framework.GetInstance&lt;ICustomerRepository&gt;();</p><p>int newId = myRepo.Save(customer);</p><p> </p><p>return newId;</p></td></tr></tbody></table>

 

By logically using vertical space and some detailed yet concise comments, the developer has noted useful information to the reader. Code should be an expression *of what* a control flow does *and* how it does it, but it rarely *records why*. Comments record the intention of the developer for future reference. Keep in mind, that code that seems extraneous or unusual to the reader may be required to operate in a specific way because of some external dependencies that are not readily apparent unless referenced in a comment.

 

<u>2.1 XML Commenting</u>

The minimum standard for XML comments is:

-   Classes must always have a &lt;summary&gt; tag.

-   Private methods in a class must have a &lt;summary&gt; tag.

-   Public methods must have complete XML documentation, including tags for a summary, return value, and any generic types.

-   Internal methods, classes and other types must have a &lt;summary&gt; tag.

-   A tag must never be empty. If an auto-generated tag is not used according to the above rules, it should be deleted.

 

<u>2.2 Commenting -- Before vs. After</u>

Comments should generally come before a line or block of code to declare its intentions, not after or on the same line.

 

Good Practice:

<table><tbody><tr class="odd"><td><p>// Tell the user that something went wrong</p><p>Console.WriteLine($"An error occurred: {errMsg}");</p></td></tr></tbody></table>

 

Bad Practice:

<table><tbody><tr class="odd"><td>Console.WriteLine($"An error occurred: {errMsg}"); // Tell the user that something went wrong</td></tr></tbody></table>

 

<u>2.3 Comment Block</u>

Developers should never use the /\* \*/ style of comments except to *temporarily* comment out a block of code during development. Use the // style instead.

 

Comment blocks are often used for permanently commenting out blocks of code that are no longer relevant. This code should be deleted. If required, it can be recovered from source control.

 

<u>2.4 Code Blocks</u>

Not every line of code requires a comment. Blocks of code that perform a common task (e.g.: populating an object) can be preceded by a line or two of comments. If a large body of code is simple enough that it doesn’t require any commentary at all, write a short comment before it summarizing its function, separated from the code by a single line of whitespace.

 

<u>2.5 Code Blocks</u>

Comments should follow a *narrative* style. The comments should describe the overall flow and logic of the code so that, if a developer were to read only the comments, they would still be able to get a fair idea of the how the code works and its control flow without needing to read the code itself.

 

<u>2.6 Do Not Write Low-Content Comments </u>

 

Avoid writing comments that simply describe what a reasonably competent developer could easily read in the code itself. E.g.:

 

<table><tbody><tr class="odd"><td><p>// Set the customer ID to 0</p><p>customer.Id = 0</p></td></tr></tbody></table>

 

Instead, describe why an action is occurring, or write nothing at all:

<table><tbody><tr class="odd"><td><p>// The customer ID must initially be set to zero so that the repository</p><p>// recognizes a the customer as new and creates an appropriate record</p><p>customer.Id = 0</p></td></tr></tbody></table>

 

<u>2.7 TODO: and FIXME</u>

Comments can include a TODO prefix to indicate low priority clean-up tasks or unimplemented features that don’t cause the code to deviate from requirements. For instance, if a section of code works but is overly complex, a comment with a TODO: prefix can be used to inform other developers that it is a good candidate for a re-write. Use a FIXME prefix to call attention to a comment describing code that is broken, deviates from requirements, may cause problems in the future or in some other way is not optional to fix. The presence of a FIXME prefix in a section of code should generally indicate that it is not yet ready for release, or that it must be fixed as a high priority.

 

Developers should configure their IDE to display tasks for FIXME tags by following these steps:

1.  On the Tools menu, click Options

2.  In the option tree view, click the Task List item under Environment.

3.  Type FIXME in the name field

4.  Set the priority to High

5.  Click Add

 

Examples:

<table><tbody><tr class="odd"><td><p>// TODO: This works but there must be a more elegant way of doing it!</p><p>// FIXME: Possible race condition! Issue # 12345</p></td></tr></tbody></table>

 

<u>2.9 Spacing and Code Grouping</u>

Use vertical white space to separate and group code into blocks of similar functionality or purpose.

-   Use a single blank line before and after a code block such as an if, for or switch statement in order to make it stand out

-   Use a single blank line before and after an important line of code that you need to draw attention to

-   Use a single blank line before and after a block of code that has a common purpose, such as setting all the properties of a newly created object

-   In general, use vertical whitespace to divide code into logical grouping of similar functionality. This allows developers or reviewers to quickly scan and understand the code

-   Do not add blank lines between multiple close braces that terminate nested code blocks.

 

3 Coding Standards and Practices

<u>3.1 Standard Class Structure </u>

The members of a class should be organized according to a standard template in this order:

-   Private class-scoped member variables

-   Constructors

-   Public properties

-   Public methods

-   Private methods

-   Simple interface implementations, such as IComparable, etc.

 

The exception to this rule is when an interface implementation makes up the bulk of a class—for instance in repository implementations. In that case, the interface implementation does not need to be separated out.

 

<u>3.2 Null-Conditional Operator </u>

Use the null-conditional operator to protect against null values:

<table><tbody><tr class="odd"><td><p>// This will ensure an exception is not thrown if location is null, and</p><p>// will set instead set locationName to null</p><p>string locationName = locationName?.Name;</p></td></tr></tbody></table>

 

However, use this operator carefully. It should only be used when the resulting value is allowed to be null. For instance, if location is null, it is actually better to throw a null reference exception when the location variable is accessed than further down the code path when the locationName variable is used:

<table><tbody><tr class="odd"><td><p>string locationName = myLocation?.Name;</p><p>..</p><p>// This code might be several thousand lines away and will cause a null // reference exception if the original customer object was null</p><p>String trimmedName = locationName.Trim();</p></td></tr></tbody></table>

 

 

<u>3.3 Use of Braces on If Structures</u>

If statements should always use braces, even if there is only a single statement that results from

the condition evaluating to true.

 

Bad Practice:

<table><tbody><tr class="odd"><td><p>if (tmpCustomer.IsNew) tmpCustomer.Save();</p><p>if (tmpCustomer.IsNew)</p><p>tmpCustomer.Save();</p></td></tr></tbody></table>

 

Good Practice:

<table><tbody><tr class="odd"><td><p>if (tmpCustomer.IsNew)</p><p>{</p><p>tmpCustomer.Save();</p><p>}</p></td></tr></tbody></table>

 

The exception to this rule is when an obvious shortcut can be taken to return from a method. There should be a single line of whitespace before and after that line:

<table><tbody><tr class="odd"><td>if (tmpCustomer.IsNew) return;</td></tr></tbody></table>

 

<u>3.4 Line Wrapping</u>

Break up lines of code that are more than 120 characters in length and indent all subsequent lines that are part of the same statement.

 

Try to find a logical place in the line to place the break. Usually the best place is after an operator. Leave the operator trailing at the end of the wrapped line (as opposed to starting the next line) to give an immediate visual cue that the statement continues on the following line.

 

Example:

<table><tbody><tr class="odd"><td><p>Console.WriteLine("Customer " + customer.Name + " has a balance of " +</p><p>customer.Balance.Dollars + " dollars and " +</p><p>customer.Balance.Cents + " cents.");</p></td></tr></tbody></table>

 

After a comma in a method declaration:

<table><tbody><tr class="odd"><td><p>private int getInternal(IParticipantReadContext readContext,</p><p>ReadSpecification querySpec, Plan referencePlan)</p></td></tr></tbody></table>

 

Before a member accessor:

<table><tbody><tr class="odd"><td><p>string customerName = customers[myCustomerNumber].PersonalInfo</p><p>.NameInfo.FirstName.Trim()</p></td></tr></tbody></table>

 

3.5 Using Parentheses

Use parentheses defensively. to make operator order obvious and to clarify the intent of a calculation.

 

<table><tbody><tr class="odd"><td><p>// Both of these lines produce the same result, but the second line is more explicit</p><p>if (foo == 3 * 7 + 4 &amp;&amp; bar != 0)</p><p> </p><p>if ((foo == ((3 * 7) + 4)) &amp;&amp; (bar!= 0))</p></td></tr></tbody></table>

 

<u>3.6 Variable Definitions</u>

Variables should be defined as close as possible to their actual usage– avoid a large block of definitions at the top of a class or method.

 

<u>3.7 Exception Handling</u>

Exceptions should only be thrown in *exceptional* circumstances. Don’t use an exception to return feedback to calling code about the normal operation of method. An exception should only be thrown if a method is unable to complete its work – the exception then indicates that processing failed completely.

 

The basic rule of exception handling is, generally speaking, don’t handle exceptions. Exceptions should only be caught in the following circumstances:

-   The code can actually do something to correct the problem. For instance, a timeout exception can be handled by retrying an operation.

-   The exception must be hidden because it may contain sensitive information that should not be shared with a caller. For instance, a web service should not return detailed information about the database error that caused an operation to fail

-   The exception has a different meaning outside of the library of class where it occurred. For instance a primary key violation in database code might indicate that a caller is attempting to add an entity that already exists in the database

 

<u>3.8 Property Guidelines</u>

Use a method instead of a property when:

-   The operation is a conversion (such as Object.ToString()) as the complexities can quickly add up and clear organization is key for future readers

-   Obtaining a property value using the Get accessor on an object modifies the state of the object

-   Calling the member twice in succession results in different results

 

Use a property getter for quick retrievals that do not involve complex side effects. For instance,

code to retrieve the next N bytes from a stream should be accessed through a method because it

has an observable side effect (i.e.: the position of the reader in the stream is updated).

 

<u>3.9 Constructors</u>

Some rules for constructors:

 

-   If a class should not be publicly creatable, specify a private default constructor

    -   By default, all classes should have private or internal constructors. Only classes that are explicitly intended for use outside the assembly should have public constructors and public visibility

-   Make proper use of protected and internal constructors

    -   Use an internal constructor when a caller outside the assembly should not be able to create a new instance of a class.

    -   Use a protected constructor when only derived classes should be able to create an instance of the base class

    -   Generally, a constructor should contain parameters that setup the class in a valid state. For instance, if a Customer class is invalid without an Address object, the constructor must contain an Address parameter (these are referred to as the invariants of the class).

>  
>
> An exception to this rule is for when a constructor can setup default state that makes the class valid. For instance, a Point2d class might take X and Y coordinates as arguments in its constructor, but a default parameter-less constructor could just set these values to 0 by default.

-   For classes with overloaded constructors, be consistent with the argument order

 

<u>3.10 Returning Arrays and Collections</u>

Members that return arrays or collections should (generally) never return null. Always prefer to return an empty collection or zero-length array, unless a null result has some special significance.

 

<u>3.11 Code for Clarity, Not Compactness</u>

Developers should place an emphasis on readability. Code should be readable and should favor clarity over compactness. Avoid excessive use of syntactical ‘tricks’ or short-hand.

 

While useful, Bad Practice:

<table><tbody><tr class="odd"><td>int nValue = (User != null) ? ((User.Active) ? User.Value1 : User.Value2) : 0;</td></tr></tbody></table>

 

Good Practice:

<table><tbody><tr class="odd"><td><p>int nValue = 0;</p><p>if (User != null)</p><p>{</p><blockquote><p>if (true == User.Active)</p><p>{</p><p>nValue = User.Value1;</p><p>}</p><p>else</p><p>{</p><p>nValue = User.Value2;</p><p>}</p></blockquote><p>}</p><p> </p><p>// Or a reasonable common ground between readability and compactness:</p><p>if (User != null)</p><p>{</p><blockquote><p>nValue = User.Active ? User.Value1 : User.Value2;</p></blockquote><p>}</p></td></tr></tbody></table>

 

<u>3.12 Avoid Excessive Vertical Whitespace</u>

Although these style guidelines make frequent recommendations to use vertical whitespace, two

blank lines should never appear consecutively in a source file.

 

<u>3.13 Using Regions</u>

Use code outlining to group the code in your source file in logical units that can be collapsed or

expanded to improve readability.

 

Examples of good units for grouping include:

-   Private ‘utility’ functions

-   Interface implementations

-   Generated code

 

When possible, group members by business function. For example:

-   Reading and writing data

-   Validation logic

Do not use outline regions to group code by visibility or scope, such as private methods, public methods, constructors, etc.

 

Structure your outlined regions so that, when closed, they are separated by a single blank line:

{Insert code snippet}

 

<u>3.15 Removing Unused Code</u>

Unreachable or unused code should be removed, unless there is a clear requirement for it to be

used in the near future. Do not comment out large blocks of code when they are no longer

required—instead, delete the unused code.

 

<u>X.X Single responsibility principle</u>:

methods (and classes) should do ONE thing. Generally, try to avoid:

-   More than 1-2 levels of nesting (if/else/switch/loops)

-   Too many parameters on methods (we prefer &lt;= 2 parameters)

-   Duplicated code and/or logic (avoid!)

-   Large methods (strongly prefer &lt;= 30 lines; methods should be small ... they should be smaller than that)

-   Names (of methods, classes, etc.) that don't give you an indication of what they are doing (usually because they are doing too many things)

-   Anytime you need to generate date/times (ex., EnteredDateTime), do it in the business tier rather than in the database (ex., SQL or Mongo)

 

<u>X.X Notable Pitfalls</u>

Avoid the following pitfalls when coding:

-   Avoid magic strings and numbers (use constants)

-   Avoid unnecessary code (using statements, functions, comments that state the obvious)

-   Avoid complicated code (prefer understandable to clear code -- ex., foreach instead of a complex LINQ statement)

-   Avoid if/else if/else/switch if at all possible (consider dictionaries unless they make code harder to understand)

-   Avoid Thread.Sleep in AATs (DevOps enforces timeouts at both test & AAT project level + they make deployments longer)

 

 

The Developer will know they are complete with this task when they have:

 

 

 

<table><tbody><tr class="odd"><td>This code block sets customer data</td></tr></tbody></table>

 

<table><tbody><tr class="odd"><td>This code block saves the customer data</td></tr></tbody></table>
