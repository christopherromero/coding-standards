Coding Standards Guide
 

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

 

<u>1.4 Naming Motivation</u>

When naming an identifier the name should be descriptive and

 

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

-   Avoid complicated code (prefer understandable to cleer code -- ex., foreach instead of a complex Linq statement)

-   Avoid if/else if/else/switch if at all possible (consider dictionaries unless they make code harder to understand)

-   Avoid Thread.Sleep in AATs (DevOps enforces timeouts at both test & AAT project level + they make deployments longer)

 

 

The Developer will know they are complete with this task when they have:

 

 

 

<table><tbody><tr class="odd"><td>This code block sets customer data</td></tr></tbody></table>

 

<table><tbody><tr class="odd"><td>This code block saves the customer data</td></tr></tbody></table>
