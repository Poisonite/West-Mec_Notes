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