# Objectives (Day 1)

* Students will be introduced to javascript by completing a tutorial website

# Server-side and Client-side Programming

* Server-side programming: Program code runs from the server hosting the website
    Advantage: Connects a servr to an online database containing information not directly accessible to end users
    Disadvantage: Use server resources and requires internet access, long delays in cases of system over-load

* Client-side programming: Programs run on the user's computer using downloaded scripts with HTML and CSS files
    Distribures load to avoid overloading of program-related requests
    Client-side programs can never replace server-side programming

# The development of JavaScript

* JavaScript is a programming language for client-side programs
* It is an interpreted language that executes a program code without using an application
* Compiler is an application that translates a program code into machine language
* JavaScript code can be directly insserted into or linked to an HTML file

# Working with the script element

* JavaScript code is attached to an HTML file using the script element
    <script scr="url"></script>
        Script can also be used without the "src" attribute to run inline javascript

# Loading the script Element

* Script element can be plaed anywhere within an HTML document

* When a browser encounters a script, it switches from loading the page and loads the javascript, then switches back

* Async and defer attributes can be added to script element, Async does same time, defer will waint until after the html has been loaded

* Async and defer are ignored in script code which in embedded into the HTML

# Creating a JavaScript Program

* JavaScript programs can be created using a standard text editor
* Adding comments to your JS Coe
    Comments help understand the design and purpose of programs
    JS comments can be enterered on single or multiple lines
        // or /* */
* Writing a JS command
    A command indicates an action for a browser to take
    A command should end in a semicolon

* Understanding JavaScript Syntax
    JS is case sensitive
    Extra whitespace between commands is ignored
    Line breaks placed within a single comand or text string causes an error

# Debugging Your Code

* Debugging: Process of locating and fixing a programming error
* Types of errors
    Load-time errors - occur when a script is first loaded by a browser
    Run-time errors - occur during execution of a script without syntax errors
    Logical mistakes but result in an incorrect output

# Opening a debugger

* Debugging tools locate and fix errors in JS
* Shortcuts to open these tools include F12 or FN+F12 depending on keyboard and OS configuration
* The tools can also be opened by selecting Developer tools from th browser menu

# Inserting a breakpoint

* A useful technique to locate the source of an error is to setup breakpoints
* Breakpoints are locations where a browser pauses a program to determine whether an error has occured at that point during execution

# Applying Strict usage of Java Script

* Strict mode enables all lapses in syntax to result in load-time or run-time errors
* To run a script as strict add the following statement to the first line of the line:
    "use strict";

# Introducing Objects

* Object: entity within a browser or webpage that has properties and methods
    Properties: define objects
    Methods: act upon objects
* JS is an object-based language that manipulates and object by changing one or more of its properties

* Types of JS Objects
    Buit-in Objects - Intrinsic to JS language
    Browser objects - Part of browser
    Document object - Part of a web document
    Customized objects - Created by programmer to use in an application

* Browser Object Model (BOM) and Document Object Model (DOM) organize the browser and document objects in hierarchical structures

# Object References

* Objects within the object hierarchy are referenced by their object names such as window, document, or navigator
* Objects can be references using the notation:
    object1.object2;
        where 1 is top in hierarchy and 2 is below

# Referencing Object Collections

* Object collections are organized into groups
* To reference a specific member of the collection use:
    collection[idref]; or collection.idref;

* Options:
    document.anchors
        selects all elements marked with an <a></a> tag
    document.applets
        selects all applets
    document.embeds
        selects all embed elements
    document.forms
        selects all forms
    document.frames
    document.images
    document.links
    document.plugins
    document.scripts
    document.styleSheets

# Referencing an Object by ID and Name

* An efficient approach to reference an element is to use its id attribute using the expression
    document.getElementById(id);
        where "id" is the value of id attribute

# Changing properties and applying methods

* Object Properties
    Object property is accessed using:
        object.property;
            Where object is a reference to an object and property is a property associated with that object
            Read-only properties can't be modified

* Applying a Method
    Object can be modified using methods
    Methods are applied using the expression:
        object.method(values);
            Wherer object is a reference to an object, method is the name of the method applied to the object, and values is a comma-separated list of values associated with the method.

# Writing HTML Code

* HTML code stored within a page element is referenced using:
    element.innerHTML()
        Where element is an object reference to an element within a web document
* Example:
    document.getElementById("dateNow").innerHTML = m/d/y<br/>h:m:s")

* Elements:
    element.innerHTML
        returns the html code within element
    element.outerHTML
        returns the html code within element as well as the html code of element itself
    element.textContent
    element.insertAdjacentHTML(position text)
        inserts HTML code defined bt text into element at position, where position is one of the following: 'beforeBegin' (before the element's opening tag), 'afterBegin' (right after the element's opening tag), 'beforeEnd' (just before the element's closing tag), 'afterEnd' (after the element's closing tag).

# Working with Variables

* Variable: named item in a program that stores a data value

* Declaring a variable
    Introducing into a script by declaring the variable using the var keyword:
        var variable = value;
            where variable is the name given to the variable and value is the value of the variable prior to any later modifications

* Conditions to assign variable names in JS
    First char must be either a lette ror an underscore char (no numbers)
    The chars after the first char can be letters numbers or underscores
    No spaces
    No names that are already declared in JS

# Variables and Data Types

* Data type: type of info stored in a variable

*Supported data types:
    Numeric value
        Any number
    Text string
        Group of characters enclosed in double or single quotes
    Boolean value
        Indicates whether the statement is true or false
    Object
        Simplifies code by removing the need to rewrite complicated object references
    Null Value
        Indicates that no value has yet ben assigned to a variale

# Working with Date + Time objects

* Date objects: Built-in JavaScript object used to store info about dates and times

* All possibilities to call: (some missing)
ahhhhhh
# Setting date and time values

* date.setDate(value)
* date.setFullYear(value)
* date.setHours(value)
* date.setMilliseconds(value)