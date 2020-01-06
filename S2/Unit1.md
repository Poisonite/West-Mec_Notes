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