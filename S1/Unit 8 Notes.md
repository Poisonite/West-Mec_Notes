#Unit 8 Notes

#Introduction to Web Tables

Web Table{
    HTML Structure that consists of multiple table rows
    Each row contains one or more table cells
    Effective tool for organizing and classifying web page content
    Consists of a table element
}

#Marking Tables and Table Rows

{
    A <table></table> element contains a collection of table rows marked using the <tr> element
    A table contains cells within each row
    Size of a table is defined by:
        Number of table rows
        Number of cells within rows
}
General Table HTML Format{
    <table>
        <tr>
            Table cells
        </tr>
        <tr>
            Table cells
        </tr>
    </table>
}

#Marking Table Headers and Table Data

Web Tables Support two Types of Table cells

Header Cells <th>{
    Contains content placed at the top of a column of beginning of a row
    By default, displays text in bold an centers text horizontally
    Marked using the th element
}
Data Cells <td>{
    Contains content within columns or rows
    By default displays text as unformatted text and is aligned to the left within the cell
    Marked using the td element
}

#Adding Table Borders with CSS

The CSS boder property is used to add borders to any part of a web table
Borders need not be of the same style
Two style choices for borders are:
    Seperated Borders
        There is border space between each cell
    Collapsed Borders
        There's no space between cells, they touch

To choose betwen separate or coppapsed borders model apply the following property to the table element{
    table{
        border-colapse: type;
    }
        Where type is either separate of collapse
        The separate borders model sets the spacing between borders using: border-spacing: 20px;
}

The Collapsed border model{
    Borders from adjacent elements are merged together to form a single border
    Borders are joined to combine their features
    Combining adjacent borders with different widths, styles, or colors is complicated
}
Five rules to reconcile the differences between adjacent borders{
    If either border has a style of hidden, the collapsed border is hidden
    Border style of none is overridden by another border style
    The style of wider borders take priority over the narrower border if neither is hidden
    Double borders have higher precedence followe by solid, dashed, ridge, outset, groove, and inset
    If borders difer only in color, precedence is given to borders
}
Precedence to borders in decreasing order{
    Bordrs around individual table cells
    Borders for table rows
    Borders for row groups
    Borders for columns
    Borders for column groups
    Borders around the entire table
}

#Spanning Rows and Columns

Spanning cells{
    Single cell that occupies more than one cell row and or column
    Created by adding rowspan or colspan attributed and covers the cells to the right and below the initial cell
}

<td colspan="cols"></td>
    Where cols is the number of columns that the cell occupies

<td rowspan="rows"></td>
    Where rows is the number of rows that the cell occupies

#Creating a Table Caption

Marked using the Caption Element{
    <caption>Content</caption>
    Where content is the content contained within the caption
    Listed immediately after the <table> tag only one caption is allowed per web table
    Inherits the text styles associated with the table
}
By default captions are placed above the tables
To specify the location, use the caption-side property{
    caption{
        caption-side: position;
    }
    Where position is either top or bottom
}

#Creating Row Groups

Row groups contain specific table information
Allows to create different styles for groups of rows
HTML supports three row groups
    Rows that belong to the table head
        Marked using thead element
    Rows that belong to the table footer
        Marked using tfoot element
    Rows that belong to the table body
        Marked using tbody element

#Creating Column Groups

Columns are determined implicitly based on the number of cells within the table rows
Columns are identified by the col element
To identify individua columns, use the id and/or class attributes

Columns can be referred using the following colgroup element{
    <table>
        <colgroup>
            Columns
        </colgroup>
        Table Rows
    </table>
        Where columns are the individual columns defined within the group
}
List of perperties accepted for columns and column groups{
    Column borders
    Background
    Width
    Visibility
}

#Exploring CSS Styles and Web Tables

Levels of precedence in the table styles in decreasing order{
    Table cells
    Rows
    Row Groups
    Columns
    Column Groups
    Table
}

#Working With Width and Height

By default, browsers attempt to fit more content in each column before wrapping the cell text
Extra space is divided ewually among columns if the width of a table is larger than its individual columns
Column widths are set using the width property

The height of each row is based on the height of the tallest cell
A uniform row height is defined by applying the height style table rows within each row group
The vertical-align property is used to move the cell text

#Applying Table Styles to other page elements (CSS)

Apply A table alyout to other HTML elements using the CSS display property{
    display: table;
    display: table-inline;
    display: table-row;
    display: table-row-group;
    display: table-header-group;
    display: table-footer-group;
    display: table-column;
    display: table-column-group;
    display: table-cell;
    display: table-caption;
}

#Tables and Responsive Design

Tables Do not scale well to mobile devices

Problems faced by users to viewa table in a modile device{
    Table is too small to read
    Table doesn't fit the visual viewport
    Tabl columns are too narrow to read the cell content
}
A New layout of table data for mobile screens is required

Several table columns are reduced to two{
    1 column contains all data lables
    The 2nd column contains the data for each label
}

To Create a responsive web table, add the text of the data tables as attributes of all id elements in the table body
Store data labels using a data attribute
General format for data attributes{
    <td data-text="value"></td>
    Where text is the mae of the data attribute and value is its value
}
Data attributes are name specific to the function it's used for
For example, the following code uses a data attribute named data-label to store the text of the labels associated with the data cell{
    <td data-label="Date">April 2, 2017</td>
}

The result is a list of data cells that are aligned as block elements
Within each block element, the data label is followed by the data cell content
The goal is to transfom table with multiple columns into two-column layout

#Designing a Column Layout

Column layout emables display of content side-by-side in a page
Layouts that use float elements or flexboxes differ from column layout

Size of a column is set using the column-count property{
    article{
        column-count: 2;
    }
    Where value is the number of columns in the layout
    Browser extensions are included to ensure cross-browser compatibility
}

#Defining Column Widths and Gaps

Columns are laid out evenly across the width of the parent element by default
To set the colummn width, use the column-width property{
    column-width: size;
    Where size is the minimun width of the column
    Column width acts like the basis value for items in a flexbox
}

The column-width and column-count properties are combined to form the shorthand columns property{
    columns: width count;
    The default gap between columns is 1em
}
To set a different gab size use the column-gap property{
    column-gap: size;
    Where size is the width of the gap
}
Another way to separate columns is with a graphic dividing line created using the column-rule property{
    column-rule: border;
    Where border defines the style of dividing line
    The bolumn-rule property can be broken into individual properties like column-rule-width, colume-rule-style, and column-rule-color
}

#Managing Column Breaks

The size of column orphans is controlled using the orphans property{
    orphans: 2;
    Where value is the minimum number of lines stranded before a column break
}
The size of column widodws is controlled using the widows property{
    widows: 2;
    Where value is the minimum numbre of lines placed after a column break
}

Other properties to define colume breaks{
    break-before: type;
    break-after: type;
    Where type is one of the following{
        ?
        ?
        ?
    }
}
To control placement of column breaks within an element, use the property{
    break-inside: auto;
    Where type is auto or avoid
}
To span cell columns, use the column-span property{
    column-span: all;
    Where span is either none to prevent spanning or all to enable the content to span across all the columns
}