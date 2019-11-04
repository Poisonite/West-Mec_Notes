# Introducing Resonsive Design:

    Page content
        Mobile - Content should be short and to the point
        Desktop - Content can be extensive giving readers the opportunity to explore all facets of the topic

    Page Layout
        Mobile - Content should be laid out within a single column, with no horizontal scrolling
        Desktop - With a wider screen size, content can be more easily laid out in multiple comumns

    Hypertext links
        Mobile - Links need to be easily accessed via a touch interfase
        Desktop - Links can be activated more precisely

    Network Bandwidth
        Mobile - Sites tend to take longer to load over cellular networks and thus overall file size should be kept small
        Desktop - Sites are quickly accesses over high-speed networks, which can mroe easily handle large file sizes

    Lighting
        Mobile - Pages need to be easily visable in outdoor lighting through the use of contrasting colors
        Desktop - Pages are typically viewed in an office setting, allowing a broader color palette

    Device Tools
        Mobile - Mobile sites often need to access devices such as phone dialing, messaging, mapping, and built in cameras
        Desktop - Sites rarly need to access device tools

    Three primary components of responsive design theory identified by Ethan Marcotte are:
        Flexibe layout so that the page layout automatically adjusts to screens of different widths
        Responsive images that resize based on the size of the viewing device
        Media queries that determine the properties of the device rendering the page so that appropriate designs can be delivered to speific devices

Introducing Media Queries

    Media Queries - Used to associate a style sheet or style rule with a specific device or list of device features
    
    To create a media query within an HTML file, add the following media attribute to either the link or style element in the document head
        media="devices"
            Where devices is a comma-separated list of supported media types associated with a specified style sheet
    
    Device types:
        All - All output devices (default)
        braille - Braille tactile feedbck devices
        Embossed - paged braille printers
        Handheld - Mobile devices with small screens and limited mandwidth
        Print - printers
        Projections - Projectors
        Screen - Computer screens
        Speech - Speech and sound synthesizers, and aural browsers
        tty - fixed width devices such as teletype machines and terminals
        tv - television type devices with low resolution, color, and limited scrollability

The @media Rule

    Media Queries can be used to assiciate speific style rules with specific devies using the following
        @media tty{
            body{font: 100;}
        }
    Where devices are supported by media types and style rules are the syle rules associated with those devices

Media Queries and Device features

    To target a device base d on its features, add the feaure and its value to the media attribute using the syntax in HTML:
        media="all/not and/or (feature:value);
            Where feature is the name of a media feature and value is the feature's value
            The and and or keywoard are used to create media queries that involve different devices or combinations of both

    Aspect-ratio - The ratio of the width of the display area relative to its height
    Color - The number of bits per color component of the output device; if the device does not support color, the value is 0
    color-index - The number of colors supported by the output device
    device-aspect-ratio - the ratio of the device-width relative to the device-height
    device-height - The height of the rendering surface of the output device
    device-width - The width of the renderingsurface of the output device
    Monochrome - the number of bits per pixel in the device's monochrome frame buffer
    Orientation - The general description of the aspect ratio: equal to portrait when the height of the display is greater than the width and equal to landscape otherwise
    Resolution - The resolution of the output device is pixels, expressed in either dpi(dots per inch) or dpcm(centimeters)
    width - The width of the display area of the output device

Applying Media Queries to a style sheet

    The mobile first principle is one in which the overall page design starts with a base style rules specific to mobile devices
    Tablet styles are applied when the screen width is 481px or greater
    Desktop styles build upon the table styles when the screen exceeds 768px

Exploring Viewports and Device width

    Web pages are viewed within a window called the Viewport

    Mobile devices have two types of view ports:
        Visual viewport - displays the webpage content that fits within a mobile screen
        Layout viewport - Contains the entire content of the page, some of which may be hidden from the user

Creating a pulldown Menu with CSS

    The following selector can be used to select the submenu that is immediately preceded by a hovered submenu title:
        a.submenuTitle:hover+ul.submenu

    In order to always keep the submenu visible as the pointer moves away from the title and hovers over the now-visible submenu, use the following:
        a.submenuTitle:hover+ul.submenu, ul.submenu:hover

Defining a Flexibe Box

    A flexible box of flexbox is a box containing items whose size can shrink or grow to match the boundaries of the box
    Items within a flexbox are laid out along a main axis
    The main axis can point in either the horizontal or vertical directions
    Cross Axis is perpendicular to the main axis and is used to define the height or width of each item

    To define an element as a flexbox, apply either of the following display styles:
        display: flex;
        display: inline-flex;
            Where a value of flex starts the flexbox on a new line and a value of inline-flex keeps the flexbox in-line with its surrounding Content

Setting the Flexbox flow

    By default, flexbox items are arranged horizontally starting from the left and moving to the right
    The Orientation ofa flexbox can be changed using:
        flex-direction: direction;
            where direction is row(default), column, row-reverse, or comumn-reverse
    The row option in a flex-direction lays out the flex items from left to right
    The comumn options creates a vertical layout starting from top moving down
    The row-reverse and comumn-reverse options layout the items bottom to top and right to left respectively

    Flex items try to fit within a single line, either horizontally or vertically
    Flex items can wrap to a new line using the following property:
        flex-wrap: type;
            Where type is either: nowrap(default) or wrap (wrapts the flex items to a new line)

Setting the Flex Basis

    The flex items are determined by three properties:
        The base size
        The growth value
        The shrink value

    The basis size defines the inital size of the tiem before the browser attempts to fit it to the flexbox

    The bais size is set using the following:
        flex-basis: valueUnits;
            Where size is one of the CSS units of measurement, which sets the inital size of the flex item
    
Define the Flex growth

    The rate at which a flex item grows from its basis size is determined by the flex-grow property
        flex-grow: value;
            Where value is a non-negative value that expresses the growth of the flex item relative to the growth of other items in the flex box
                The default flex-grow value is 0, which is equlivalent to the flex item remaining at its base valueUnits

Define the Shrink rate

    The rate at which flexboxes shrink below their basis size is given by the following property:
        flex-shrink: value;

    Where value is a non-negative value that expresses the shrink rate of the flex item relative to the shrinkage of the other items of the flexbox
    The default flex-shrink value is 1
    If the flex-shrink value is set to 0, then the flex item will not shrink below its basis value

# The flex property

    The syntax for the flex property is:
        flex: grow shrink basis;
            Where grow defines the growth of the flex item, shrink proviedes its shrink rate, and basis sets the item's inital size
        Default value:
            flex: 0 1 auto;
                Which automatically sets the size of the flex item to match its content of the value of its width and height property
    
    The flex property supports the following keywords:
        auto - use to automatically resize the item from its defualt size (ewulivalent to flex: 1 1 auto;)
        inital - The default value (equlivalent to flex 0 1 auto;)
        none - Use to create and inflexable item that will not grow or shrink (same as flex: 0 0 auto;)
        inherit - use to inherit the flex values of its parent element

Reordering Page Content with flexboxes

    The flexbox model allows to place the flex items in any order using the following order property:
        order: value;
    
    Where value is an integer where items with smaller order values are placed before items with larger order values

Aligning items along the main axis

    By defualt, flex items are laid down at the start of the main axis
    To specify a different placement apply the following justify-content property:
        justify-content: placement;

Aligning Items Along the Main Axis:

    Where placement is one of the following keywords:
        Flex-start - Items are places at the start of the main axis (defualt)
        flex-end - Items are placed at the end of the main axis
        space-between - Items are distributed evenly with the first and last item aligned with the start and end of the main axis
        space-around - Items are distributed evenly along the main axis with eqyal space between them and the ends of the flexbox

Aligning Flex Lines:

    The align-content property is simular to the justify-content property except that it arranges multiple lines of content along with flexbox's cross axis

    The syntax of the align-content property is:
        align-content: value;
            Where value is any of the same keywords as placement

Aligning items along hte cross axis

    The align-items property aligns each flex item about the cross axis
    Syntax:
        align-items: value;
            Where value is 1 of the keywords:
                Flex-start - Items are places at the start of the cross axis
                flex-end - Items are placed at the end of the cross axis
                center - items are centered along the corss axis
                stretch - items are stretched to fill up the cross axis (default)
                baseline - items are positioned so that the baselines of their content align
    
    The align-items property is only impactful when there is a single line of flex items
        Use for single line
    The align-content property is used to layout the flexbox content for multiple lines of flex items
        Use for multi-line

    To align a single item out of a line of flex items, use the following align-self property:
        align-self: center;
            where value is one of the alignment choices supported by this property (regular flex options)

Creating a Navicon Menu

    Navicon - Used to indicate the presence of hidden navigation menus in mobile webistes
    The Navicon is a symbol represented as three horizontal lines
    When a user hovers or touches the navicon the navigation menu is revealed

Designing for printed media

    To apply a print style sheet, the media attribute is used in the link elements to target stylesheets to either screen devices or print devices

Working with the @page rule

    Every printed page in CSS is defined as a page box
    Page box is composed of two areas:
        page area - Contains the content of the document
        margin area - contains the space between the printed content and theedges of the page
    Styles are applied to the page using:
        @page{
            align-self: center;
        }

Designing for Printed Media{
    To apply a print style sheet, the media attribute is used to the link elements to target style sheets to either screen devices or print devices
}

Working with the @page Rule{
    Every printed page in CSS is defined asa page box
    Page box is composed of two areas:
        Page area - Contains the content of the document
        Margin area - contains the space between the printed content and the edges of the page
    Styles are applied to the page box using:
    @page{
        align-self: center;
    }
}

Setting the Page Size{
    The following size property allows web authors to define the dimensions of a printed page:
        size: width height;
            Where width and height are the width and height of the page
    The keyword auto allows prowsers to determine the page dimensions
    The keyword inherit inherits the page size from the parent element
}

Using the Page Pseudo-classes{
    Different styles can be defined for different pages by adding the following:
        @page:pseudo-class{
            style: rules;
        }
            Where pseudo-class is first for the first page of the print out, left for the pages that appear on the left in the double-sided printouts, or right for pages that appear on the right in double-sided printouts
                EX: :first, :left, right
}

Page Names ant the Page property{
    To define styles for pages other than the first, left, or right, create a page name as follows:
        @page name{
            style: rules;
        }
            Where name is the label given to the page
    
    To assign a page name to an element use:
        selector{
            page: name;
        }
            Where selector identifies the element that will be displayed on its own, and name is the name of a previously defined page style
}

Formatting Hypertext Links for Printing{
    To append the text of a link's URL to the linked text, apply the following style rule:
        a::after{
            content: " (" attr(href)")";
        }
            This style rule uses the after pseudo-element to add the URL for a hyperlink directly after the hyperlink for print purposes (or any purpose)

    THe word-wrap property is used to break long text strings at arbitary points if it extends beyond the boundaries of its container
}

Working with page breaks{
    Page breaks can be inserted either directly before or after an element, using the following properties:
        page-break-before: type;
        page-break-after: type;
            Where type has the following possible values:
                always - use to always place a page break before or after the element
                avoid - use to never palce a page break
                left - Use the place a page break where the next page will be a left page
                right - Use to plae a page break where the next page will be a right page
                auto - Use to allow the printer to determine whether or not to insert a page break
                inherit - Use to insert the page break style from the parent element
}

Preventing Page Breaks{
    Page breaks can be prevented by using the keyword avoid in the page-break-after or page-break-before properties
    For example, the following style rule prevents page breaks from being added after any heading:
        h1, h2, h3, h4, h5, h6{
            page-break-after: avoid;
        }
}

Working with Wiows and Orphans{
    Page breaks within block elements, such as paragraphs, often leave behing widows and Orphans
    A widow is a fragment of text left dangling at the top of a page
    An orpan is a text fragment left at the bottom of a page

    To control the size of widows and orphans, CSS supports the following properties:
        widows: value;
        orphans: value;
            Where value is the number of lines that must appear within the element before a page break can be inserted by printer
                EX:
                    widows: auto;
                    widows: 2;
}