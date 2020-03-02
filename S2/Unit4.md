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
* An object that contians properties and methods associated wit a acciubt
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