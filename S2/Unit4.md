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

## Day 2 ##

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