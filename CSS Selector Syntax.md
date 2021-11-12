# [[CSS]] Selector Syntax
#CSS #HTML

#### General Form:
selector {property: value}

#### Universal Selector:
<pre>
* {
  property: value;
}
</pre>

#### Type Selector:
ex. div: 
<pre>
div {
  property: value;
}
</pre>

#### Class Selector:
In the HTML: `<div class="class-name"></div>`

In the CSS: 
<pre>
.class-name {
  property: value;
}
</pre>
- Not required to be unique, so can be used on many elements.
- Multiple classes can be added to a single element as a space-separated list.
	- ex: `<div class="class1 class2">`
- Never use spaces in class names

#### ID Selectors
Selects an element with the given ID
In the HTML: <div id="title"></div>
In the CSS: 
<pre>
#title {
  property: value;
}
</pre>
In most cases you should use classes and not IDs.
An element can only have **one** ID, and it cannot be repeated on a single page.

#### Grouping Selector
What to do when two groups of elements share some of their style declarations
To cut down repetition you can group selectors together as a comma-separated list
ex:<pre> .class1, .class2 {
  property1: value; 
  property2: value;
}</pre>

#### Chaining Selectors
Selecting elements that share classes
<pre> 
.class1.class2 {
  property: value;
}
</pre>

#### Descendant Combinator
Causes elements that match the last selector to be selected if they also have an ancestor that matches the previous selector
In the HTML:
<pre>&lt;div class="parentClass"&gt;
  &lt;div class="childClass"&gt;
    &lt;p>content&lt;/p&gt;
  &lt;/div&gt;
&lt;/div&gt;</pre>
In the CSS:
<pre>
.parentClass .childClass {
	property: value;
}
</pre>
In this example the only element affected would be one of class childClass, with an ancestor with a class of parentClass