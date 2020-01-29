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

# exploring the while loop
* while loop: command block that is run as long as a specific condition is met
* condition in a while loop does not depend on the value of a counter variable
* general cyntax for a while loop:
    + while(bool === true) {commands}

# exploring the do/while loop
* do/while loop: generally used when the program loop should run at least once before testing the stopping condition
* tests the condition to continue the loop right after the latest command block is run
* structure of the do/while loop:
    + do{
        commands
    } while (bool === true);

# comparison and logical operators
* comparison operator: compares the value of one expression to another, returning a boolean value indicating whether the comparison is true or false

+ ==
    - tests whether x is equal in value to y
+ ===
    - tests whether x is equal in value and type to y

+ !=
    - tests whether x is not equal to y

+ >,>=,<, <=
    - tests x is greater, less, or equal to y

* logical operators allow several expressions to be connected

+ && meands and
+ || means or
+ ! means not

# program loops and arrays:
* program loops: cycle through different values contained within an array
* general structure to access each value from an array using a for loop
    + for (var i = 0; i < array.length; i++) {
        commands involving array[i];
    }

# array methods to loop through arrays
* JS supports several methods to loop though the contents of an array without having to create a program loop structure
* each of these methods is based on calling a function that will be applied to each item in the array

* general syntax:
    + array.method(callback[thisArg])
        - where callback is the name of the function that will be applied to each array item
        - thisArg: A callback to optional arguments that can be included to passa value to the function
* General syntax of the call back function:
    + function callback(value[index/array]){commands}
        - where value is the value of the array item during each pass through the array
        - where index is the numberic index of the current array item
        - where array is the name of the array
        - only the value parameter is required, the rest are optional

# running a function for each array item
* forEach() method: runs a function for each item in the array
* general syntax:
    + array.forEach { notes not completed!!}

# mapping an array
* map() method: the function called returns a value that can be used to map the contents of an existing array into a new array
    - var x = [3,8,12]
        var y = x.map(doubleIt);
        function doubleIt(value){
            return 2*value;
        }

# filtering an array
* filter() method: extracts array items that match some specified condition
    + array.filter(callback[arg])
        - where callback is a function that returned a boolean value of true or false or each item in the array
        - array items that return a value of true are copied into the new array

* every() method: returns true if every item in the array matched the condition specified by the callback function, otherwise returns false
* some() method: returns true if some array items match a conditio nspecified in the function and otherwise returns false if none of the items match the condition

+ reduce(callback[arg])
    - reduces array by keeping only those items that return a value of true from the callback function
+ reduceRight(callback[arg])
    - reduces array from the last element moving left by keeping only those items that return a value of true from the callback function

+ find(callback[arg])
    - returns the value of the first element in the array that passes a test in the callback function
+ findIndex(callback[arg])
    - returns the index of the first tlement in the array that pases a test in the callback function

# introducing conditional statements
* parallel array:
    - each entry in the array matches or is parallel to an entry in the other array
* conditional statement
    - runs a command or command block only when certain circumstances are met

# exploring the if statement
* the most common conditional statement is the if statement
* general structue of the if statement:
    + if(bool === true){commands}

* conditional statement uses the same comparison and logical operators that are used with program loops
* modulus operator: %
    - returns the integer remainder after dividing 1 interger by another

* if else statement: chooses between alternate command blocks
    - runs 1 command block if the conditional expression is true and a different command block if the expression is false
* general structure:
    + if(bool === true){commands if true} else{commands if false}

# exploring the break command
* break statement: terminates any program loop or conditinal statement
* used anywhere within the program code
* when a break statement is encountered, control is passed to the statement immediately following it
* it is most often used to exit a program loop before the stopping condition is met

# exploring the continue command
* continue statement:
    - stops processing the commands in the current iteration of the loop and continues on to the net iteration
    - it is used to jump out of the current iteration if a missing or null value is encountered

# exploring statement labels
* statement label:
    - identifies statements in JS code so they can be used elesewhere in the program
    - syntax of label
        + label: statements
            - where label is the text of the label and steatements are the statements identified by the label