# Introducing the Monthly Calendar
* The calendar should appear in the form of a web table with links to specific events placed within the table cells
* Appearane and placement of the calendar will be set using a CSS style sheet
* The program created should be easily adaptable so that it can be used to create other monthly calendars

# Reviewing the Calendar Structure
* Names and IDs assigned to the different parts of the table
    - The entire caledar is set in a web table with the ID calendar_table
    - Cell containing the calendar title has the ID calendar_head
    - Seven cells containing the days of the week abbreviations all belong to the class calendar_weekdays
    - All cells containing the dates of the month belong to the class calendar_dates
    - the cell containing the current date has the ID calendar_today
* Class and ID desgnations make it easier for page developers to assign different styles to ther different parts of the calendar

# Adding the calendar() function
* Place the commands that generate the calendar within a single function named createCalendar()
* Inital code to generate the calendar
    + {
        var thisDay = new Date("august 24, 2018");
        document.getElementByID("calendar").innerHTML = createCalendar(thisDay);

        function createCalendar(calDate){
        var calendarHTML = "<table id='calendar_table'>";
        calendarHTML += "</table>"
        return calendarHTML;
        }
    }

# Introducing Arrays
* getMonth() method: extracts a month number
* getFullYear() method: extracts the 4 digit year value
* The date method doesn't return 

* array
    - A collection f values organized under a single name
* index
    - the number that each individual value is associated with and that distinguishes it from other values in the array (starting with 0)
* Array values are refferenced using the expression array[i]
    - where array is the name of the array and [i] is the index of a specific value in the array
        - monthName[4] references the fifth month in the array (5th element)

# Creating and Populating an Array
* to create an array, apply the object constructor
    - where array is the name of the object and the legnth is the parameters
    - The legnth value is optional, if the legnth parameter is omitted then the array expands automatically, as more items are added
* An array can be populated with values by specifying both the array name and the index number of the array item
* command to set the value of a specific item in an array:
    + array[i] = value;
        - where value is the value assigned to the array element with the index value matching i

* Populate the entire array in a single statement using the following command:
    + var array = new Array(values);
        where values is a comma-separated list of the values in the array
* Array literal
    - creates an array in which the array values are a comma-separated list within a set of brackets;
    + var array = [values];
        - where values are the values of the array
* Array values need not be of the same data type
* mix of numeric values, text strings, and other data types within a single array is allowed
    + EX: var x = ["april", 3.14, true, null];

# Working with Array Length
* JS array automatically expands in length as mroe items are added
* Apply the following length propery to determin the array's current size
    + array.length;
        - The value returned by the length property is equal to one more than the highest index number in the array

* sparce array: creates (in JS) in which some of the array values are undefined
* the length value is not always the same as the number of array values
* occurs frequently in database applications
* value of the length property cannot be reduced without removing items from the end of the array

# Reversing an Array
* items are placeed in an array either in the order in which they are defined or explicitly by index number, by default
* JS supports 2 methods for changing the order of the array items
    + reverse()
        * Reverses the order of items in an array, making the last items first and the first items last
    + sort()
        * Rearranges array items in alphbetical order
        * when applied to numeric values will sort the values in order by their leading digits, rather than their numberical values
        * based on comparison of two adjacent array item values, the finction returns a negative, positive, or 0 value
            - if a negative value is returned than a is plaed before b
            - if a positive value is returned, then b is placed before a
            - if a zero value is returned, a and b retain their original positions

# Sorting an array
* function to sort numberic values in ascending order:
    + function ascending(a, b) {
        return a - b;
    }
* function to sort numberic values in descending order:
    + function ascending(a, b) {
        return b - a;
    }
* the compare function is applied to the sort() method as follows
    + array.sort(fname);
        - where fname is the name of the compare function
            + Ex: monthName.sort(ascending);

# Extracting and inserting an array item
* splice(): Removes and inserts array items
    + array.splice(start, size, values);
        - start is the starting index to splice in the array, size is the number of array items to remove including the start index, and values is an optional comma-separated list ov values to insert into the array
            - if no values are specified, the splic method will remove the specified amount of items from the array
        - the splice command always alters the original array

# using arrays as data stacks
* stack: arrays ca nalso be used to store info in a data structure
* new items are added to the top of the stack or to the end of the array
* a stack data structure employs the last-in first-out (LIFO) principle
* in the LIFO principle the last items added to the stack are the first ones removed

* push() method: appends new items to the end of an array
    + array.push(values);
        - where values is a comma-separated list of values to be appended to the end of the array
* pop() method: removes or unstacks the last item
    + array.pop();

* queue: employs the FIFO (first-in-first-out) principle in which the first item added to the data list is the first removed
    - this is sumular to a stack
* shift() method: removes the first array item
* unshift() method: inserts new items at the front of the array

# array Methods
+ copyWithin(target, start[,end])
    - copies items within the array to the target index, starting with the start inded and ending with the ootional end index
+ concat(array1, array2, ...)
    - Joins the array to two or more arrays, creating a single array containing the items from all the arrays
+ fill(value,[,start][,end])
    - fills the array with items having the value, starting from start index and ending at the end index
+ indexOf(value [,start])
    - searches the array, returning the index number of the first element equal to value, starting from the optional start index
+ join(separator)
    - joins all items in the array into a single text string, the array items are separated using the text in teh separator parameter. if no spearator is specified, a comma is used
+ lastIndexOf(value, [,start])
    - searches backwors through the array returning the index number of the first element to equal value, starting from the optional start index
+ pop()
    - removes the last item from the array
+ push(values)
    - appends the array with new items, where values is a comma-separated list
+ reverse()
    - reverses the order of the items in the array
+ shift()
    - removes the first item from the array
+ slice(start, stop)
    - extracts the array items starting with the start index up to the stop index, returns a new sub-array
+ splice(start, size, values)
    - extracts the size items from the array starting with the tiem with the index start. to insert new items int othe array, specify the array items in a comma-separated values list
+ sort(functionName)
    - sorts the array where functionName is the name of a function that returns a positive, negative, or 0 value. if no function is specified, the array is sorted in alphabetical order
+ toString()
    - converts the contents of the array to a text string with the array values in a comma-separated list
+ unshift(values)
    - inserts new items at the start of the array, where values is a comma-separated list of new values

# working with program loops
* program loop: set of commands executed repeatedly untill stopping condition is met
* two most commonly used program loops in js are for loops and while loops

# exploring the for loops
* in a for loop, a variable know as a counter var is used to track the nubmer of times a block of commands is run
    - when the counter var reaches or exceeds a specified value, the for loop stops
        - general for loop structure:
            + for(start; continue; update){commands}
                - where start is an expression that sets the inital value of a counter var
                - where continue is a boolean expression that must be true for the loopto continue
                - where update is an expression that indicates how the value of the counter var should change each time through the loop
                - where commands is any command that should run each loop cycle