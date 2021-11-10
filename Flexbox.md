#CSS 
# Flexbox
A way of manipulating elements in [[CSS]]

Flexbox is a way to arrange items into rows or columns, where those items will flex (i.e. grow or shrink) based on some simple rules that you can define. Flexbox is used in order to be able to make complex layouts. 

Flexbox isn't a single property, but a toolbox. 

- A *flex container* is any element that has <code>display: flex;</code> on it. 
- A *flex item* is any element that lives directly inside of a flex container. 

An element can be both a flex container and a flex item. 

## Flex shorthand
The <code>flex</code> declaration is a shorthand for 3 properties of a flex item:
<code>flex-grow, flex-shrink, and flex-basis</code>. 

The **default value** of the flex property is <code>flex-grow:0; flex-shrink: 1; flex-basis: 0%:</code>
The actual default value for <code>flex-basis</code> is <code>auto</code>, but when you specify <code>flex: 1;</code> it's interpreted as <code>flex: 1 1 0;</code>

#### flex-grow
Expects a single number as its value, which is used as the items **growth-factor**. If all items have <code>flex-grow: 1;</code>, then they grow the same amount. If, however, one item is set to <code>flex-grow: 2;</code>, then that item will take up twice as much space as the others.

#### flex-shrink
Expects a single number as its valuue, which is used as the items **shrink-factor**. <code>flex-shrink</code> is only applied if the size of all flex items is larger than their parent containers. With all items having <code>flex-shrink: 1;</code> then they will shrink evenly. 
With <code>flex-shrink: 0;</code> an item will *not* shrink. 
You can specify higher values to <code>flex-shrink</code> to make items shrink at a higher rate. 

#### flex-basis

<code>flex-basis</code> sets the initial size of the item. Any sort of <code>flex-grow</code>ing or <code>flex-shrink</code>ing starts from that baseline size. 
With a value of <code>auto</code> the item will take up what the space that the contents need.

Using <code>auto</code> as a flex-basis tells the item to check for a width declaration of the flex items.

#unsure
#### flex in practice
Generally, you’re most likely to use declarations like <code>flex: 1;</code> to make divs grow evenly and <code>flex-shrink: 0</code> to keep certain divs from shrinking.


## Axes
The default direction for a flex container is horizontal, or <code>row</code> but you can change the direction to vertical, or <code>column</code>.

Specifying direction: 
<pre>.flex-container {
	flex-direction: column;
}</pre>


## Alignment
<code>justify-content</code> aligns the items inside a flex container across the *main axis*.
Values accepted are 
- <code>center</code>
	- centers all items in a cluster in the middle of the container
- <code>space-between</code>
	- places the items with even space *between* them

<code>align-items</code> aligns the items along the *cross-axis*

When the <code>flex-direction</code> is changed, then the behaviour of <code>justify-content</code> and <code>align-items</code> changes, because they're based on the main and cross axis.

#### Gap
<code>gap</code> adds a specified space between flex-items, similar to margins. 


## Other flex arguments
<code>flex-wrap</code> allows the flex items to wrap to new lines when needed. 

