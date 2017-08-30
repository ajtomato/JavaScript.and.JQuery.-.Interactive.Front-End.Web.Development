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

## 4. Decisions & Loops

## 5. Document Object Model

## 6. Events

## 7. jQuery

## 8. Ajax & JSON

## 9. APIs

## 10. Error Handling & Debugging

## 11. Content Panels

## 12. Filtering, Searching & Sorting

## 13. Form Enhancement & Validation
