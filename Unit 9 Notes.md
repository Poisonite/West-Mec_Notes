#Introducing Web Forms

Web Forms{
    Allows users to enter data that can be saved and processed
    Common way to accept user input
    Allows the creation of interactive websites for user feedback
}

#Parts of a Web Form

Controls, also known as widgets, are the objects that allow a user to interact with a form
Each data entry control is associated with a data field
Data field{
    stores the data values supplied by a user
}
Types of controls{
    Input boxes - Insert text and numeric values
    Option/radio buttons - select data values from a predefined set of options
    Selection lists - select data values from an extensive list of options
    Check Boxes - select data values limited to two possiblilites such as Yes or No
    Text area boxes - eter text strings that may include several lines of content
}

Types of widgets{
    Spin boxes - enter integer values confined to a specified range
    Slider controls - enter numberic values confined to a specified range
    Calendar controls - select date and time values
    Color pickers - choose color values
}

#Forms and Server-Based Programs

Feedback from the server can be sent back to the browser
Data from the web orm is sent to a program running on the server

#Starting a Web Form

Web forms are marked with the form element{
    Ex: <form id="text" attributes>Contents</form>
        Id identifies the form
        Attribuets specify how the form should be processed by the borwser
        content is the form's content
}
A form element can be placed anywhere within the body of a page
Forms also contain page elements such as tables, paragrphs, inline images, and headings

#interacting with a Web Server

The action, method, and enctype attributes have to be included in a form to specify where and how to send the form data
Ex{
    <form action="url" method="type" enctype="type">Content</form>{
        action attribute - provides the locaton of the web server program that processes the form
        method attrubite - specifies how the browser should send form data to the server
            Two possible values for method attribute{
                Get method - tells the browser to append the form data to the end of the URL specified in the action attribute
                    The get method is the default method
                Post method - sends the form data in its own separate data stream
                    The post method is considered to be a more secure form of data transfer
            }
        enctype attribute - specifies how the form data should be encoded as it is sent to the server
    }
}
The enctype attribute has three possible values
application/x-www-form-urlencoded
    THe defualt format is which the data is encoded as a long text string with spaces replaced by the +character and special characters(includeding tab and line breaks) replaced with their hexadecimal code values
Multipart/form-data
    The format used when uploading files in which no encoding of the data values occurs
Text/plain
    The format in which data is transferred as plain text with spaces replaced with the + character but no other encoding of the data values occur

A script element is an HTML element used to access and run JavaScript programs that will run within the user's browser

#Creating a Field Set

Field set - groups fields that share a common purpose
Field sets are created usingthe fied set element{
    <fieldset id="id">Content</fieldset>{
        Id intentifies the field set
        Content is the form content within the field set
    }
}

#Adding a Fieldset legend

Legend describes the content of a field set using the legend element{
    <legend>Text</legend>
}
The legend element contains only text and no nested elements
by default, legends are placed in the top left corner of the field set box and can be moved to a different locatuon using the css positioning styles

#Coreating input boxes

Syntax for the input element{
    <input name="name" id="id" type="type" />
    The name attribute provides the name of the data field associated with the control
    The id attribute identifies the control in which the user enters the field value
    The type attribute indicates the data type of the field
}
Input box types:
Button
Checkbox
Color - User can select a color
Date
Datetime-local - calendar date and time
Image
Month - month and year
Number
Radio - raido or option button
Password - Text box where chars are *
Range - a slider
reset - resets web form
search
submit - submits the form
tel - phone numbers
text
time - select time only
url
week - select a week range

#Input Types and virtual keyboards

Virtual keyboards are software repersentations of a physical device
Web forms can be made reponsive by displaying different virtual keyboards for each input type

#Adding field labels

To associate a text string with a control, the text string has to be enclosed within the label element{
    <label for="id">Label Text</label>
    Id is the id of the control that is associated with the label
    Label text is the text of the label
}

#Defining default values and placeholers

The value attribute is used to specify a default field value
Placeholders - text strings that appear within a form control, providing a hint about the kind of data that should be dntered int oa field
They are defined using the placeholder attribute{
    placeholder="text"
        Where text is the text of the placeholder
}

#Entering Date and Time Values

Date and time fields ensure that users enter data in the correct format
Indincated using type attribute: date, time, datetime-local, month, and week

#Creating a selection list

A selection list is a list box that presents users with a group of possible values for the data field

The list is created using the select and option elements{
    <select name="name">
    <option value="value1">Text 1</option>
    <option value="value2">Text 2</option>
    </select>
}

#Working with select attributes

By defualt, a selection list appears as a drop-down list box
to display a selection list as a scrool box, use the size attribute to the select element{
    <select size="value">...</select>
}
By default, selections allow one 1 selection
to allow more than 1 item to be selected add the multiple attribute{
    <select multiple></select>
}

#grouping selection options

Organize selection list options by placing them in option groups usng the optgroup element{
    <select>
        <optgroup label="label1">
        <option>text1</option>
        <option>text2</option>
        </optgroup>
    </select>
}

#Creating Option Buttons

Option buttons are also called radio buttons

Unlike selection lists, the optons appear as separate controls in the web form
They are created with a goup of input elements with a type attribute value of "radio"
    Radio indicates that only 1 option may be selected

EX{
    <input name="name" value="value1" type="radio" />
    <input name="name" value="value2" type="radio" />
        Where name is the name of the data field and value1, value2, value 3, are fields associated with each option
        set an option button to be selected as default by adding "checked" to the end of the input element attributes section as an attribute
}

#Creating a Text Area Box

Text area is created using the textarea element{
    <textarea name="name"></textarea>
}

HTML supports the rows and cols attibutes to set the text area size{
    <textarea rows="value" cols="value"></textarea>
    Rows attribute specifites the number of lines in the text area box
    Cols attribute specifies the nymber of characters per line
}

#Entering Numberic Data

Creatting a spinner control
    spinner control displays an up or down arrow increase or decrease the feild value by a set amount
    To create a spinner control, apply the input element using the number data type

#Suggesting options with data lists

Data list: A list of possible data values that a form field can have
Data lists are defined using the data list element{
    <datalist id="id">
    <option value="value" />
    <option value="value" />
    </datalist>
}

#Working with Form Buttons

Form buttons - A type of form control that performs an action
Actions performed{
    Run a command from a program linked to the web form
    Submit the form to a program running on the web server
    Reset the form fields to their defualt values
}

#Creating a command Button

Command button - Runs a program that affects the content of a page or the actions of a browser
Created using the input element with the type attribute set to button{
    <input value="text" onclick="script" type="Button" />
        Text is text that appears on the button
        Script is the name of the program code that's run when the button is clicked by the user
}

#Creating a submit and reset button

Submit button - submits a form to the server for processing when clicked
Submit button is created using input elements with the type attribute set to submit and reset respectivly{
    <input value="text" type="submit" />
        where text is the strign that appears on the button
}

#Designing a custom button

The appearance of a command submit and reset button is determined by the browser

for more control over a buttons appearance use the button element{
    <button type="text">Content</button>
        Type attribute specifies the button type
        content are html elements placed within the button
}

#Validating a web form

Validation - Process of ensuring that a user has supplied valid data

Types of validation:
    Server-side validation - validation occurs on the web server
    Client-side validation - validation occurs in the user's browser

#Identifying required values

The first validation text is to vrify if data is supplied for all the required data fields

Add he required attribute to the control to identify the required attribute to the control to identify the required data fields

If a required field is left blank, the browser will not submit the form returning an error message to indicate

#Validating based on data type

A form fails the validation test if the data values entered into a field don't match the field type
EX{
    A data field with the number tye will be rejected if nonnumeric data is entered
}

#Testing for a valid pattern

To test whether a field value follows a valid pattern of characters, test the character string againsnt a regular expression

Regular expression or regex is a concise description of a characer pattern

to validate a text value against a regular expression, add the pattern attribute to the input element

#Defining the Legnth of the field value

THe syntax to define the max legnth attribute is{
    <input maxlegnth="value" />
        Max legnth doesn't care if it's a char or a digit
}

#Applying inline validation

Inline validation - the technique of immediate data validation and reporting of errors
The focus pseudo-class is used to change the dispaly style of fields that currently contain invalid data
Focus - the state in which an element has been clicked by the user (making it the active control on the form)

Inline validation types{

    Checked
    Defualt
    Enabled
    Focus
    Indeterminate
    In-range
    Optional
    Out-of-rrange
        A field that falls outside the required range
    Required
    Valid
}

#Pseudo-classes for Valid and invalid Data

The Valid and invalid pseudo-clases are used to format controls based on whether their field values pass/fail a validation test