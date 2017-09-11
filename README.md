# JavaScript and JQuery: Interactive Front-End Web Development

## 1. The ABC of Programming

### What is a script and how do I create one?

### How do computers fit in with the world around them?

The models use objects to represent physical things. Objects can have:

* properties that tell you about the object
* methods that perform tasks using the properties of that object
* events which are triggered when a user interacts with the computer

The browser represents each window or tab using a *window* object. The *location* property of the *window* object will tell you the URL of the current page.

The current web page loaded into each window is modelled using a *document* object. The *title* property of the *document* object tells you what is between the opening *\<title\>* and closing *\</title\>* tag for that web page, and the *lastModified* property of the *document* object tells you the date this page was last updated.

The *document* object represents an html page.

When the browser creates a model of a web page, it not only creates a *document* object, but it also creates a new object for each element on the page. Together these objects are described in the *Document Object Model*.

### How do I write a script for a web page?

* CONTENT LAYER: .html files, this is where the content of the page lives. The HTML gives the page structure and adds semantics.
* PRESENTATION LAYER: .css files, the CSS enhances the HTML page with rules that state how the HTML content is presented (backgrounds, borders, box dimensions, colors, fonts, etc.).
* BEHAVIOR LAYER: .js files, this is where we can change how the page behaves, adding interactivity.

Most of the scripts are added just before the closing \</body\> tag (this is often considered a better place to put your scripts).

JavaScript runs where it is found in the html.

## 2. Basic JavaScript Instructions

Comments are same as C++.

Declare the variable:

    var variableName = 3;

Until you have assigned a value to a variable, programmers say the value is *undefined*. Technically, *undefined* is a data type like a number, string, or Boolean.

JavaScript distinguishes between numbers, strings, and *true* or *false* values known as Booleans. In addition to these three data types, JavaScript also has others (arrays, objects, undefined, and null). Unlike some other programming languages, when declaring a variable in JavaScript, you do not need to specify what type of data it will hold.

The string data type is enclosed within a pair of quotes. These can be single or double quotes, but the opening quote must match the closing quote.

Escaping: using a backwards slash (or "backslash", i.e., "\") before any type of quote mark that appears within a string.

The values in the array do not need to be the same data type.

The array literal (shown in the first code sample) is preferred over the array constructor when creating arrays.

* array literal

        var a = ['hello', 2, true];
        a[0];

* array constructor

        var a = new Array('hello', 2, true);
        a.item(0);
    
Each array has a property called *length*, which holds the number of items in the array.

    var l = a.length;

## 3. Functions, Methods & Objects

Function declaration

    function functionName(parameter1, parameter2) {
        return parameter1 + parameter2;
    }
    var v = functionName(1, 2);

Functions can return more than one value using an array.

If you put a function where the interpreter would expect to see an expression, then it is treated as an expression, and it is known as a *function expression*. In function expressions, the name is usually omitted. A function with no name is called an *anonymous function*.

    var area = function(width, height) {
        return width * height;
    };
    var size = area(3, 4);

IMMEDIATELY INVOKED FUNCTION EXPRESSIONS (IIFE)

    var area = (function() {
        var width = 3;
        var height = 2;
        return width * height;
    }());

Anonymous function expressions and IIFEs are used for code that only needs to run once within a task, rather than repeatedly being called by other parts of the script.

* As an argument when a function is called (to calculate a value for that function).
* To assign the value of a property to an object.
* In event handlers and listeners to perform a task when an event occurs.
* To prevent conflicts between two scripts that might use the same variable names.

If you create a variable outside of a function, then it can be used anywhere within the script. It is called a *global* variable and has *global scope*.

The same value can be used with more than one variable. The following value is shared by two variables.

    var isWall = true;
    var canPaint = true;

Creating an object: literal notation

    var hotel = {
        name: 'Park',
        roomRate: 240, // Amount in dollars
        discount: 15,  // Percentage discount
        offerPrice: function() {
            var offerRate = this.roomRate * ((100 - this.discount) / 100);
            return offerRate;
        }
    };

You can also access the properties of an object (but not its methods) using square bracket syntax.

    var hotelName = hotel['name'];

The *new* keyword and the object constructor create a blank object. You can then add properties and methods to the object.

    var v1 = new Ojbect();
    var v2 = {}
    v1.name = 'Hello'
    delete v1.name;

Object constructor:

    function Hotel(name, rooms, booked) {
        this.name = name;
        this.rooms = rooms;
        this.booked = booked;
        this.checkAvailability = function() {
            return this.rooms - this.booked;
        };
    }
    var quayHotel = new Hotel('Quay', 40, 25);

The name of a constructor function usually begins with a capital letter (unlike other functions, which tend to begin with a lowercase character).

Under the hood, the *this* keyword is a reference to the object that the function is created inside.

When a function is created at the top level of a script (that is, not inside another object or function), then it is in the *global scope* or *global context*. The default object in this context is the *window* object. so when *this* is used inside a function in the *global context* it refers to the *window* object.

If a named function has been defined in global scope, and it is then used as a method of an object, *this* refers to the object it is contained within.

Another scenario to mention is when one function is nested inside another function, but the value of *this* can vary (depending on which browser you are using). You could work around this by storing the value of *this* in a variable in the first function and using the variable name in child functions instead of this.

If the *var* keyword is not used, the variable is declared in *global scope* (you should always use it).

The Browser Object Model creates a model of the browser tab or window.

    window: current browser window or tab
      |
      +----- document: current web page
      |
      +----- history: pages in browser history
      |
      +----- location: url of current page
      |
      +----- navigator: information about browser
      |
      +----- screen: device's display information

In JavaScript there are six data types:

1. String
2. Number
3. Boolean
4. Undefined: a variable that has been declared, but no value has been assigned to it yet
5. Null: a variable with no value - it may have had one at some point, but no longer has a value
6. Object

Undefined and null values do not have objects.

## 4. Decisions & Loops

String can use ==, <, or > directly.

Strict equal to: ===, compares two values to check that both the data type and value are the same.

Strict not equal to: !==, compares two values to check that both the data type and value are not the same.

Data types can be coerced from one type to another.

## 5. Document Object Model

The DOM is neither part of HTML, nor part of JavaScript; it is a separate set of rules. It is implemented by all major browser makers, and covers two primary areas:

1. Making a model of the html page
2. Accessing and changing the html page

DOM is stored in the browser's memory. It consists of four main types of nodes.

* document node: the root of DOM tree
* element node: html element
* attribute node: a part of element which carries the html element attribute
* text node: the text in the element

DOM queries

* Select an individual element node
    * getElementById()
    * querySelector(): use a CSS selector, and return the first matching element
* Select multiple elements
    * getElementsByClassName()
    * getElementsByTagName()
    * querySelectorAll()
* Traverse between element nodes
    * parentNode
    * previousSibling/nextSibling
    * firstChild/lastChild

DOM methods can also be used on element nodes within the page to find descendants of that node.

Live & static nodelists:

* In a live Nodelist, when your script updates the page, the Nodelist is updated at the same time. The methods beginning *getElementsBy_* return live Node lists.
* In a static Nodelist when your script updates the page, the NodeList is not updated to reflect the changes made by the script. The new methods that begin *querySe1ector_* (which use CSS selector syntax) return static Nodelists.

Traversing the DOM can be difficult because some browsers add a text node whenever they come across whitespace between elements.

Get/update element content:

* *nodeValue*: access & update a text node with *nodeValue*
* *textContent*: the *textContent* property allows you to collect or update just the text that is in the containing element (and its children). The update will also include any markup.
* *innerHTML*: *innerHTML* is used both to retrieve and update content. To update an element, new content is provided as a string. It can contain markup for descendant elements.

DOM manipulation

* createElement()
* createTextNode()
* appendChild()
* insertBefore()
* removeChild()
* getAttribute()
* hasAttribute()
* setAttribute()
* removeAttribute()

## 6. Events

## 7. jQuery

## 8. Ajax & JSON

## 9. APIs

## 10. Error Handling & Debugging

## 11. Content Panels

## 12. Filtering, Searching & Sorting

## 13. Form Enhancement & Validation
