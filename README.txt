CSS Fundamentals

1. CSS Styling
- HTML <style></style> scripts: 
    + <head>
        <style>
            ...
        </style>
    </head>
- CSS stylesheets: 
    + <head>
        <link rel="stylesheet" href="style.css" type="text/css" />
    </head>
- CSS style rule/syntax: 
    + <selector>{
        <propertyname> : <value>; 
        ... 
        <propertyname> : <value>;
    }
- CSS selectors: 
    + simple selectors: 
        - <element>{
            > select all <element> elements
        }
        -  <element1>,...,<elementN>{
            > select all <element1>,...,<elementN> elements
        } 
        - .<class>{
            > select all elements with class=<class>
        } 
        - .<class1>.<class2>...{
            > select all elements with class=<class1> && class=<class2> &&...
        } 
        - #<id>{
            > select the element with id=<id>
        }
        - * {
            > select all elements 
        } 
    + combinator selectors:
        - descendant selector: (space)
            + <element1> <element2> ...{
                > select all <element2> that is descendant of <element1> 
                > Note: direct or indirect children
            }
            + .<class1> .<class2> ...{
                > select all element with class=<class2> that is descendant of element with class=<class1>
            } 
        - child selector: (>)
            + <element1>><element2>{
                > select all <element2> where direct parent is <element1> 
                > Note: only direct children with 1 inhertance level difference
            } 
        - adjacent sibling selector: (+)
            + <element1>+<element2>{
                > select all <element2> that placed immediately after <element1> 
            } 
        - general sibling selector: (~)
            + <element1>~<element2>{
                > select every <element2> that preceded by <element1>
            }
    + attribute selectors: 
        - (optional:<element>)[ <attribute> ]{
            > select all (specific <element>) elements with target <attribute>
        } 
        - [<attribute> = value]{
            > select all elements with <attribute>="value"
        } : 
        - [<attribute> ~= value]{
            > select all elements with <attribute> containing word "value"
            > Note: "value" has to be a whole word or followed by a hyphen ( - )
        } 
        - [<attribute> *= value]{
            > select all elements with <attribute> containing "value"
            > Note: "value" do NOT have to be a whole word
        }
        - [<attribute> |= value]{
            > select all elements with <attribute> starting with "value" 
            > Note: "value" has to be a whole word or followed by a hyphen ( - )
        } 
        - [<attribute> ^= value]{
            > select all elements with <attribute> begins with "value"
            > Note: "value" do NOT have to be a whole word
        } 
        - [<attribute> $= value]{
            > select all elements with <attribute> ends with "value"
            > Note: "value" do NOT have to be a whole word
        } 
    + pseudo-class selectors: 
        - <element>:<pseudo-class> {
            > pseudo-class: used to define a special state of an element
            > :active | :checked | :disabled | :empty | :enabled | :first-child | :first-of-type | :focus | :hover | :in-range | :invalid | :lang(language) | :last-child | :last-of-type | :link | :not(selector) | :nth-child(n) | :nth-last-child(n) | :nth-last-of-type(n) | :nth-of-type(n) | :only-of-type | :only-child | :optional | :out-of-range | :read-only | :read-write | :required | :root | :target | :valid | :visited 
        }
    + pseudo-element selectors: 
        - <element>::<pseudo-element>{
            > pseudo-element: used to style specified parts of an element
            > ::after | ::before | ::first-letter | ::first-line | ::selection
        }
- CSS property values: 
    + keywords: 
        - thin, thick, larger
    + absolute measurements: 
        - cm
        - mm
        - in : 1in == 96px == 2.54cm
        - px : 1px == (1/96 * 1in)
        - pt : 1pt == (1/72 * 1in)
        - pc : 1pc == 12 pt
    + relative measurements: 
        - em : relative to the font-size of the element   
        - rem : relative to font-size of the root element
        - ch : relative to width of the "0" (zero)
        - vw : relative to 1% of the width of the viewport
        - vh : relative to 1% of the height of the viewport
        - vmin : relative to 1% of viewport's smaller dimension
        - vmax : relative to 1% of viewport's larger dimension
        - % : relative to the parent element
        * viewport = the browser window size. If the viewport is 50cm wide, 1vw = 0.5cm.
    + color codes: 
        - Hexadecimal colors: #RRGGBB
            >  #ff0000
        - RGB colors: rgb(red, green, blue)
            > rgb(0,0,0) ==  rgb(0%,0%,0%)
            > rgb(255,255,255) ==  rgb(100%,100%,100%)
        - RGBA colors: rgba(red, green, blue, alpha opacity)
            > rgba(0, 0, 0, 0.0)
            > rgba(255, 255, 255, 1.0)
        - HSL colors: hsl(hue, saturation, lightness)
            > hsl(0, 0%, 0%)
            > hsl(360, 100%, 100%)
        - HSLA colors: hsla(hue, saturation, lightness, alpha opacity)
            > hsla(0, 0%, 0%, 0.0)
            > hsla(360, 100%, 100%, 1.0)
        - Predefined color names: 
            > ex. blue, red, coral, brown, ...
        - <currentcolor> Keyword: 
            > refers to the value of the color property of an element
    + text: 
        - text color: 
            > <color>: 
            > <background-color>: 
        - text alignment: 
            > <text-align>: <center|left|right|justify>
            > <vertical-align>: <top|middle|bottom>
        - text decoration: 
            > <text-decoration>: <none|overline|underline|line-through>
        - text transformation: 
            > <text-transform>: <uppercase|lowercase|captialize>
        - text spacing: 
            > <text-indent>:
            > <letter-spacing>:
            > <word-spacing>:
            > <line-height>:
            > <white-space>: 
        - text shadow: 
            > <text-shadow>: top right bottom left color 
    + fonts: 
        - <font-family>: <specific font-family>, ... , <generic font-family>;
            > font family:ex. Times New Roman, Arial, Comic Sans, Impact, Courier New
            > font collection:ex. serif, sans-serif, cursive, fantasy, monospace
        - <font-size>: <absolute|relative measurements>;
            > absolute: px
            > relative: em 
        - <font-style>: <normal|italic|oblique>;
        - <font-weight>: <normal|bold>;
        - <font-variant>: <normal|small-caps>;
        - <font->: shorthand property to specify all the individual font properties in one property
    + funcitonal notations: 
        - <background>: url(...); 
        - <background-color>: rgb(0,0,0); 
        - <border-color>: rgb(0,0,0); 
        - ...

2. CSS Styling Rules
- CSS rules applied in DESCENDING order: 
    1. importance: css !important; overrule ALL|html <style></style>|<global style="">
    2. specificity: higher > lower specificty/inheritance 
    3. source order: cascade
- CSS stylesheets applied in DESCENDING order: 
    1. important declarations in user style sheets (custom styles set by client users)
    2. important declarations in author style sheets (custom styles set by developers)
    3. normal declarations in author style sheets (custom styles set by developers)
    4. normal declarations in user style sheets (custom styles set by client users)
    5. default declarations in user agent style sheets (browser's default styles)
- Cascade: 
    +  ORDER of CSS rules matter when two rules have EQUAL SPECIFICITY the one that comes LAST will be used.
    +  LAST order of EQUAL SPECIFICITY also used with multiple CSS stylesheets
        > <h1>This is my heading.</h1>
        h1 { 
            color: red; 
        }
        h1 { 
            color: blue;    <IN-USE>
        }     
- Specificity: 
    + [A B C]
        > A: count of <id> selectors
        > B: count of <class/attribute> selectors
        > C: count of <element> selectors 
        > *     :   a=0 b=0 c=0 >>> specificity=0   (lower specificity)
        > li    :   a=0 b=0 c=1 >>> specificity=1 
        > ul li :   a=0 b=0 c=2 >>> specificity=2 
        > li.red:   a=0 b=1 c=1 >>> specificity=11 
        > #uid  :   a=1 b=0 c=0 >>> specificity=100 (higher specificity)
    + <element selector> is LESS specific — will select all elements of that type that appear on a page which getting a lower score.
    + <class selector> is MORE specific — will select only the elements on a page that have a specific class attribute value which getting a higher score.
        > <h1 class="main-heading">This is my heading.</h1>
        .main-heading { 
            color: red;     <IN-USE>
        }
        h1 { 
            color: blue; 
        }      
- Inheritance: 
    + SOME CSS property values set on parent elements are inherited by their child elements using DOM inheritance 
        > ex. font, list
    + SOME CSS properties do NOT inherit parent elements 
        > ex. width, margin, padding, box models
        > <p>We can change the color by targetting the element with a selector, such as this <span>span</span>.</p>
        body {
            color: blue;    <IN-USE>
        }
        span {
            color: black;   <IN-USE>
        }
    + inheritance control values: 
        > <property> : inherit; 
        Sets the property value applied to a selected element to be the same as that of its parent element
        > <property> : initial;
        Sets the property value applied to a selected element to the initial value of that property
        > <property> : unset;
        Resets the property to its natural value, which means that if the property is naturally inherited it acts like inherit, otherwise it acts like initial.
- Reset.css: 
    + short compressed (minified) set of CSS rules that resets the styling of all HTML elements to a consistent baseline.
        > /* CSS Reset */
        #element { margin:0; padding:0; font-size:100%; line-height:1; }
        ...
        /* #element rules: */
        #element { margin:5px 0 10px; font-size:13px; line-height:1.5; }



3. CSS Element Box Model 
- Box Model: ALL elements
    + margin (transparent area outside border)
        border (opaque border)
            padding (transparent area insider border & around content)
                content (opaque text/media)
    + <div> {
        <width> : content
        <height>: content
        <padding>: top right bottom left
        <border>:
        <margin>: top right bottom left
        }
        > total element width = Twidth + left/right padding + left/right border + left/right margin
        > total element height = height + top/bottom padding + top/bottom border + top/bottom margin
- Vertical margins collapse: 
    + top & bottom margins of blocks sometimes combined/collapsed into a single margin with 
        > largest size of individual margins 
    + horizontal margins do NOT collapse/overlap
- Display & Visibility property: 
    + <display>: 
        > none: completely removed & NOT reserve space
        > block: display as block element starts on new line takes up whole width
        > inline: display as inline element any height/width properties effect ignored
        > inline-block: display as inline element but can apply height/width properties
        > ...
        > initial/inherit: CSS inheritance controls
    + <visiblity>:
        > visible: element is visible (default)
        > hidden: not visible but reserve space
        > collapse: ONLY for table <tr>, <tbody>,  <col>, <colgroup>
        > initial/inherit: CSS inheritance controls



4. CSS Element Layout   
- Normal flow:  
    + layout:
        > default browser HTML layout wihtout any layout controls
    + <display> property: parent element for direct children elements 
        > block: display as block element starts on new line takes up whole width
        > inline: display as inline element any height/width properties effect ignored
        > inline-block: display as inline element but can apply height/width 
        > run-in: displays as either block/inline element depending on context
- Floats: 
    + layout: 
        > designed to change element behavior and the block level elements that follow it in normal flow
    + <float> property:  applying a float value can cause block level elements to wrap alongside of an element
        > <float>: <none>
        > <float>: <left>
        > <float>: <right>
        > <float>: <inherit>
        > <clear>: <both|left|right>  
- Positioning: 
    +  layout
        > designed to move element from where would be placed in normal flow to another location.
    + <position> property: allows you to precisely control the placement of boxes inside other boxes
        > <position>: <static> 
            > default element placement in normal flow
        > <position>: <relative> 
            > move element with specification relative to its normal flow position
        > <position>: <fixed> 
            > similar to relative positioning except that it fix element relative to the browser viewport NOT another element.
            > useful for browser toolbars
        > <position>: <absolute> 
            > moves element completely out of page's normal flow,
        > <position>: <sticky> 
            > act like <position>: <static> until it hits a defined offset from the viewport then it acts like <position>: <fixed>
- Table: 
    + layout: 
        > designed to lay out elements that are not tables which sometimes described as "using CSS tables".
        > <form>, <div>s, and <label>s and <input>s have been told to display like a table, table rows, and table cells respectively
    + <display> property: 
        > table: display element like block-level <table> element
        > inline-table: display element like inline-level <table> element
        > table-caption: display element like block-level <caption> element
        > table-header-group: display element like block-level <thead> element
        > table-row-group: display element like block-level <tbody> element
        > table-column-group: display element like block-level <colgroup> element 
        > table-footer-group: display element like block-level <tfoot> element
        > table-cell: display element like inline-level <td> element
        > table-column: display element like block-level <col> element
        > table-row: display element like block-level <tr> element
- Flexbox: 
    + layout: 
        > designed for 1D layout with a block-level flex container either as a row/column
    + <display> property: parent element for direct children elements 
        > flex: display element as block-level flex container
        > inline-flex: display element as inline-level flex container
    + flex container properties:
        > <flex-direction>: <row|row-reverse|column|column-reverse>
        > <flex-wrap>: <wrap|nowrap|wrap-reverse>
        > <flex-flow>: shorthand for <flex-direction> & <flex-wrap>
        > <justify-content>: horizontal <center|flex-start|flex-end|space-around|space-between>
        > <align-items>: vertical <center|flex-start|flex-end|stretch|baseline>
        > <align-content>: <center|flex-start|flex-end|space-around|space-between>
- Grid: 
    + layout: 
        > designed for 2D layout with block-level grid container lining up in rows and columns
    + <display> property:
        > grid: display element as block-level grid container
        > inline-grid: display element as inline-level grid container
    + grid container properties:
        > <grid-template-columns>: <>
        > <grid-template-rows>: <>
        > <justify-content>: <>
        > <align-content>: <>
- Multicol:
    + layout: 
        > designed to layout content in columns as block-level multicol container
        > 1-column (often used for mobile)
        > 2-column (often used for tablets/laptops)
        > 3-column layout (only used for desktops) 
    + multicol container properties:
        > <column-count>: <>
        > <column-width>: <> (unequal/equal columns)

5. CSS Responsive Design: 
    + design criteria: 
        - fluid grids
            > multicol layout
            > flexbox layout
            > grid layout
        - fluid text/images
            > responsive images
            > responsive typography
        - media query
            > changable/adaptable layouts depending on viewport sizes