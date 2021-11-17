# jsStrings 
Characters in strings can be escaoed by using \

## Concatenating strings
Concatenate means "join together". Joining together strings in JS uses the plus (`+`) operator. 

## Template literals
Template literals are **not** supported in IE, but are supported by most other browsers.

Another type of string syntax is **template literals**. Template literals are written with *backticks*, while tradition strings use  single or double quotes. 

Template literals can use *placeholders* when you want to include a variable or expression inside a string, by placing it inside a `${ }` construct. 

In order to split a traditional string over multiple lines, a newline character, \n ,has to be included. Template literals, however, respect the line breaks in the source code, so newline characters are no longer needed. 

# jsStringMethods
All string methods return a new string. They don't modify the original string.  
Formally said: Strings are immutable: Strings cannot be changed, only replaced.

### String Length
The `length` property returns the length of a string. EX:
<pre>
let txt = "text";
let txtlength = txt.length;
</pre>

### Extracting String Parts
Three methods for extracting a part of a string: 
- `slice(start, end)`
- `substring(start, end)`
- `substr(start, length)`

### slice() Method
`slice()` extracts a part of a string and returns the extracted part in a new string. The method takes 2 parameters: the start positions, and the end position (end not included). EX:
```` JavaScript
let str = "Apple, Banana, Kiwi";  
let part = str.slice(7, 13);
````
This example sets the part variable to banana.

If a parameter is **negative**, the position is counted from the end of the string. EX: 
```` JavaScript
let str = "Apple, Banana, Kiwi";  
let part = str.slice(-12, -6);
````

If you omit the second parameter, the method wiill slice out the rest of the string

### substring() Method
`substring()` is similar to `slice()`.
The difference is that `substring()` cannot accept negative indexes. EX: 
```` JavaScript
let str = "Apple, Banana, Kiwi";  
let part = substring(7, 13);
````

### substr() Method
`substr()` is similar to `slice()`.The difference is that the second parameter specifies the **length** of the extracted part.
```` JavaScript>
let str = "Apple, Banana, Kiwi";  
let part = str.substr(7, 6);
````

### replace() Method
The `replace()` method replaces a specified value with another value in a string: EX:
```` JavaScript>
let text = "Please visit Microsoft!";  
let newText = text.replace("Microsoft", "W3Schools");
````

- By default, the replace() method
	- replaces only the first match
	- is case sensititve
		- To replace case *insensitive*, use a **regular expression** wtith an /i flag
- To replace all matches use a regualar expression with a /g flag (global match)

### Converting to Upper and Lower Case
A string is converted to upper case with `toUpperCase()`
A string is converted to lower case with `toLowerCase()`:

### The concat() Method
`concat()` joins two or more strings
The `concat()` method can be used instead of the plus operator.

### String.trim()
The `trim()` method removes whitespace from both sides of a string

### Extracting String Characters
There are 3 methods for extracting string characters:
-   `charAt(_position_)`
-   `charCodeAt(_position_)`
-   Property access [ ]

### charAt()
The `charAt()` method returns the character at a specified index (position) in a string

### charCodeAt()
The `charCodeAt()` method returns the unicode of the character at a specified index in a string

The method returns a UTF-16 code (an integer between 0 and 65535).

### Property Access
ECMAScript 5 (2009) allows property access [ ] on strings:

- Property access might be a little **unpredictable:**
	- It makes strings look like arrays (but they are not)
	- If no character is found, [ ] returns undefined, while charAt() returns an empty string.
	- It is read only. str[0] = "A" gives no error (but does not work!)

### Converting a String to an Array
A string can be converted to an array with the `split()` method.

If the separator is omitted, the returned array will contain the whole string in index [0].

If the separator is "", the returned array will be an array of single characters:

## String Properties

|Property|Description|
| - | - |
|constructor|Returns the string's constructor function
|length|Returns the length of a string|
|prototype|Allows you to add properties and methods to an object|

## String Methods

|Method|Description|
| - | :- |
|charAt()|Returns the character at the specified index (position)|
|charCodeAt()|Returns the Unicode of the character at the specified index|
|concat()|Joins two or more strings, and returns a new joined strings|
|endsWith()|Checks whether a string ends with specified string/characters|
|fromCharCode()|Converts Unicode values to characters|
|includes()|Checks whether a string contains the specified string/characters|
|indexOf()|Returns the position of the first found occurrence of a specified value in a string|
|lastIndexOf()|Returns the position of the last found occurrence of a specified value in a string|
|localeCompare()|Compares two strings in the current locale|
|match()|Searches a string for a match against a regular expression, and returns the matches|
|repeat()|Returns a new string with a specified number of copies of an existing string|
|replace()|Searches a string for a specified value, or a regular expression, and returns a new string where the specified values are replaced|
|search()|Searches a string for a specified value, or regular expression, and returns the position of the match|
|slice()|Extracts a part of a string and returns a new string|
|split()|Splits a string into an array of substrings|
|startsWith()|Checks whether a string begins with specified characters|
|substr()|Extracts the characters from a string, beginning at a specified start position, and through the specified number of character|
|substring()|Extracts the characters from a string, between two specified indices|
|toLocaleLowerCase()|Converts a string to lowercase letters, according to the host's locale|
|toLocaleUpperCase()|Converts a string to uppercase letters, according to the host's locale|
|toLowerCase()|Converts a string to lowercase letters|
|toString()|Returns the value of a String object|
|toUpperCase()|Converts a string to uppercase letters|
|trim()|Removes whitespace from both ends of a string|
|valueOf()|Returns the primitive value of a String object|

All string methods return a new value. They do not change the original variable.

## String HTML Wrapper Methods

The HTML wrapper methods return a string wrapped inside an HTML tag.

These are not standard methods, and may not work as expected.

|Method|Description|
| - | - |
|anchor()|Creates an anchor|
|big()|Displays a string using a big font|
|blink()|Displays a blinking string|
|bold()|Displays a string in bold|
|fixed()|Displays a string using a fixed-pitch font|
|fontcolor()|Displays a string using a specified color|
|fontsize()|Displays a string using a specified size|
|italics()|Displays a string in italic|
|link()|Displays a string as a hyperlink|
|small()|Displays a string using a small font|
|strike()|Displays a string with a strikethrough|
|sub()|Displays a string as subscript text|
|sup()|Displays a string as superscript text|

A **method** is a bit of functionality that is build into the language or into specific data types. 