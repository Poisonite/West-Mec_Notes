## Working with Events and Styles - CS 102 Unit 4 ##

# Introducing JS Events
* JS programs run in response to events
* Events: Actions initiated by the user or by the browser
    - Ex:
        - Clicking an object
        - Closing a web page

# Creating an event handler
* Event Handler: A property that controls how an object will respond to an event
* Event handler waits until the event occurs and then responds by running a function or command block to execute an action
* Event handlers can be added to a page element using the following attribute:
    + <element onevent="script()"></element>
* Event Handlers can also be defined as object properties using the command:
    + objectName.onevent = function();
        - Where object is the object in which the event occurs, event is the name of the event, and function is the name of a function run in response to the event

# Event handler events:
* Onbeforeunload
    - When page is about to be unloaded by the browser
* Oncopy
    - When the user copies the content of an element
* Oncut
    - When the user cuts the content of an element
* Onerror
    - When an error occurs while loading an external file like a video or image which won't load
* Onload
    - After the page has finished loading
* Onpaste
    - when the user pastes some content into an element
* Onresize
    - when browser window is resized
* Onunload
    - When the page is unloaded bt the browser (or browser window is closed)

# Creating an event handler
* The challenge lies in determining which button was clicked
* theres no way of knowing which puzzle to load into the page without knowing with button activated the onclick event handler
* This info can be determined using the event object

# Using the Event Object
* An object that contains properties and methods associated wit a acciubt
    - EX: THe action of clicking a mouse button generates an evetn whc

* Event object is passed as an argument to the function handling the event to retreieve the info contained in the evet object
    + function myFunction(evt){
        Function code.
    }
    - Where evt is the name assigned to the parameter when receiving the event from the handler

# Event object list:

* evt.bubbles
* evt.cancelable
    - returns a boolean value indicating whether the event can have its default action can have its default action canceled
* Evt.currentTarger
* evt.defaultPrevented
* evt.target
* evt.eventPhase
* evt.isTrusted
* evt.timeStamp
* evt.type
* evt.view
* evt.preventDefault()
* evt.stopImmediatePropagation()
* evt.stopPropagation()

# Exploring Object Properties
* JS object props that mirror HTML attributes follow certain conventions
* All JS props must begin with a lowercase letter
* if the HTML attribute consists of multiple words, JS property follows a format know as camel case

# Exploring Object Properties
* If the name of the HTML attribute is a reserved JS name or keyword, the corresponding JS property is often prefaced with the text string html
* class attribute is an exception to this convention because the class name is reserved by JS for other purposes
* References to the HTML class attribute use the className property

# Object props and inline styles
* Inline styles for each page element can be applied using the following style attribute
    + <element style="property:value">
        - where:
            - element is teh page element
            - property is a CSS style property
            - Value is the value assigned to that property
* The equivalent command in JS is:
    + object.style.property = 'value';
        - With property written in camel case
        - Inline styles have precedence over the style sheets

# Creating Object Collections with CSS Selectors
* In JS, to change the background color of all table cells, you must first define an object collection based on a CSS selector using the following querySelectorAll() method:
    + document.querySelectorAll(selector);
        - Where selector is the CSS selector that the object collection is based on

* Once the object collection has been defined, change the background-color style of each td element by applying the backgroundColor property to the objects in the object collection
* Reference only the first element that matches a selector pattern using the following JS method:
    + document.querySelector(selector);
        - where selector is a css selector

# Working with Mouse Events
* JS supports events associated with the mouse such as clicking, right-clicking, double-clicking and moving the pointer over and out of page elements

# Mouse and pointer events (some are missing)
* click
* contextMenu
* dbclick
* mousedown
* mouseenter
* mouseleave
* mousemoove
* mouseout
* mouseover
* mouseup
* select
* wheel

# Working with Mouse Events (pt2)
* A mouse action can be comprised of several events
* The action of clicking the mouse button is comprised of three events, fired in the following order
    - Mouse down (button pressed)
    - Mouse up(button is released)
    - click (the button has been pressed and released)
* The event object for mouse events has a set of properties that can be used to give specific info about the state of the mouse

# Mouse event object properties
* evt.button
    - Returns a number indication that mouse button that was pressed, where 0=left, 1 = wheel or middle, and 3 = right and evt is event object for the mouse event
* evt.buttons
    - returns a number indicating the mouse button or buttons that where pressed, where 1 = left, 2=right, 4=wheel/middle, 8=back, 16=forward, and other multiple buttons are indicated by the sum of their numbers
* evt.clientX
    - Returns the horizontal coord in pixels of the mouse pointer relative to the browser window
* evt.clientY
    -returns the vertical coord in pixels of hte mouse pointer relative to the browser window
* evt.detail
    - returns the number of times the mouse button was clicked
* evt.pageX
    - returns the horizontal coordinate in pixels of the mouse pointer relative to the document
* evt.pageY
    - returns the vertical coordinate in pixels of the mouse pointer relative to the document
* evt.which
    - returns a number indication the mouse button that was pressed, where 0=none, 1=left, 2=middle, and 3 =right
* evt.relatedTarget
    - references the secondary target of the event, for the mouseover event this is the element that the pointer is leaving and for the mouseout event it's the element that the pointer is entering
* evt.screenX
    - returns the horizontal coordinate of the mouse pointer relative to the physical screen
* evt.screenY
    - Returns the vertical coordinate of the mouse pointer relative to the physical screen

# introducing the event model
* event model: describes how events and objects interact within the webpage and web browser
* The process is when a single event is applied to a hierarchy of objects is part of the model

* once an event has been initiated, it propagates through the object hierarchy in 3 places
    - capture phase: the event moves down the object hierarchy starting from the root element (browser window) and moving inward until it reaches the object that initiated the event
    - Target phase: the event has reached the target of the event object and no longer moves down the object hierarchy
    - bubbling phase: the event propagates up the object hierarchy back to the root element (browser window) where the propagation stops

* limitations of event handlers
    - event handlers respond to events during the target phase but do not recognize the propagation of events through the capture and bubbling phase
    - only 1 function can be applied to an event handler at a time

# Adding an event listener
* Event listener: listens for events at the propagate through the capture target and bubble phases, allowing the script to respond to an event within any phase
* unlike event handlers, more than 1 function can be applied to an event using listeners

* add a listener to an object by applying the addEventListener() method
    + object.addEventListener(event, function [capture = false]);
        - where
            - object is the object in which the event occurs
        - capture is optional

# removing an event listener
* the event model allows you to remove event listeners from the document by applying the removeEventListner()method
    + object.removeEventListener(event, function [capture = false]);
        - where object, event, function, and capture have same meaing as add eventlistner method

# controlling event propagation
* the browser has its own default responses to events
* apply the following preventDefault() method to the event object to rpevent the occurrence of the browser's default actions
    + evt.preventDefault()

* alternatively, you can prevent the browser's default action by returning the value false from the event handler function
* the return false statement doesn't prevent default actions if event listeners are used in place of event handlers

# exploring keyboard events
* JS supports the keydown, keypress, and keyup events that allow users to interact with page with keyboard
* The keydown and keypress events are simular the differene being 
* the value associated with a key event property is affected by the event itself
* for the keypress event, the charCode, keyCode, and which are properties all return a unicode char num
* modifier keys: akt, ctrl, shift, command keys
* in addition to char keys JS supports the modifier keys through the use of the altKey, ctrlKey, shiftKey, and metaKey props 

# keyboard events

* keydown
* keypress
    - key is pressed down and rekease resyktubg ub cgar beubg ttoed
* keyup
    - key is released
* evt.altKey
    - looks for shift key pressed
* evt.ctrlKey
    - looks for control key pressed
* evt.charCode
    - looks for unicode UTF8 HTML charcode pressed
* evt.key
    - returns txt of key used in event
* evt.keyCode
    - returns the unicode char code of the ke used in the keypress event or the keycode used in the keydown or keyup events
* evt.shiftKey
* evt.location
    - returns location number of key where 0 is located in standard pos, 1 is on the keyboards left edge, 2 is on the keyboards right edge, and 3 is on the num pad
* evt.metaKey
    - command key on MacOS keyboards and Windows key on MSWindows keyboards
* evt.which
    - returns unicode char code of the key used in the keypress event or the keycode used in the keydown or keyup events

# Changing the cursor style
* Cursors can be defined using the following CSS cursor style
    + cursor: cursorTypes;
        - where cursorTypes is a comma-separated list of cursor types

* JS command to define cursors is as follows:
    + object.style.cursor = cursorTypes;
        - Where object is the page object that will display the cursor style when hovered over by the mouse pointers

* Create a customized cursor from an image file using url(image) where image is an image file

* by default, the click point for a cursor is locate in the top-left corner of the cursor image at the coordinates (0,0)
* specify a different location by adding the (x,y) coordinates of the click point to the cursor definition as follows:
    + url(image) x y
        - where x is the x-coordinate and y is the y-coordinate of the click point in pixels

# Working with functions as objects
* Everything in JS is an object, including functions
* anything that can be done with an object can be done with a function, including:
    - storing a function as var
    - storing a function as object property

# Working with functions as objects
* using one function as a parameter in another function
* nesting one function within another function
* returning a function as the result on another function
* modifying the properties of a function

# Function declarations and function Operators
* the following hello() function is created using the function declaration format
    + function hello() {
        alert("Welcome to Hanjie!");
    }
* Function operator: the definition of the function becomes the variable's "value"
    + var hello = function () {
        alert("Welcome to Hanjie!");
    }

# Function declarations and function operators
* The two ways fo defining the hello() function differ in how they are stored
    - functions defined with a function declaration are created and saved as the browser parses the code prior to script running
        - since the function is already stored in memory the statements that run the function can be placed prior to the statement that declares the function

* Function operators are evaluated as they appear in the script after parsing
    - function operators are more flexible than function declarations, allowing a function to be placed anywhere a var can be placed

# Anonymous functions
* Anonymous functions have function declaration whith out the function name
* more notes i missed :(

* Functions that are named are called named functions
* Anonymous functions are more concise and easier to manage because the function is directly included with the expression that invokes it
* Anonymous functions limit the scope of the function to be exactly where it's needed

# Passing variable values into anonymous functions
* JS supports two types of variables
    - global vars: declared outside ant function

* global vars should be avoided when possible because:
    - global vars are accessible to every function in the application
    - the task of tracking which functions are using and modifying the global vars becomes

* an advantage of using Anonymous functions is that they reduce the need for global vars because they perform their actions locally within a function
* one of the challenges of the anonymous functions is keeping track of all of the nested levels of functions and procedures

# displaying dialog boxes
* JS supports confirmation and prompt dialog boxes
    + alert(text);
        - displays a message where you press OS
    + confirm(text);
        - displays a message where you can choose to cancel
    + prompt(text [defaultInput]);
        - prompt where info can be entered