#CSS 
# cssFlexbox
A way of manipulating elements in [[CSS]]

Flexbox is a way to arrange items into rows or columns, where those items will flex (i.e. grow or shrink) based on some simple rules that you can define. Flexbox is used in order to be able to make complex layouts. 

Flexbox isn't a single property, but a toolbox. 

- A *flex container* is any element that has `display: flex;` on it. 
- A *flex item* is any element that lives directly inside of a flex container. 

An element can be both a flex container and a flex item. 

### Flex shorthand
The `flex` declaration is a shorthand for 3 properties of a flex item:
`flex-grow`, `flex-shrink`, and `flex-basis`. 

The **default value** of the flex property is `flex-grow:0`, `flex-shrink: 1`, and `flex-basis: 0%`.
The actual default value for `flex-basis` is `auto`, but when you specify `flex: 1;` it's interpreted as `flex: 1 1 0;`

### flex-grow
Expects a single number as its value, which is used as the items **growth-factor**. If all items have `flex-grow: 1;`, then they grow the same amount. If, however, one item is set to `flex-grow: 2;`, then that item will take up twice as much space as the others.

##### moziall on flex-grow 
With the `flex-grow` property set to a positive integer, flex items can grow along the main axis from their `flex-basis`. This will cause the item to stretch and take up any available space on that axis, or a proportion of the available space if other items are allowed to grow too.

If we gave all of our items in the example above a `flex-grow` value of 1 then the available space in the flex container would be equally shared between our items and they would stretch to fill the container on the main axis. 
The flex-grow property can be used to distribute space in proportion. If we give our first item a `flex-grow` value of 2, and the other items a value of 1 each, 2 parts will be given to the first item (100px out of 200px in the case of the example above), 1 part each the other two (50px each out of the 200px total).

### flex-shrink
Expects a single number as its valuue, which is used as the items **shrink-factor**. `flex-shrink` is only applied if the size of all flex items is larger than their parent containers. With all items having `flex-shrink: 1;` then they will shrink evenly. 
With `flex-shrink: 0;` an item will *not* shrink. 
You can specify higher values to `flex-shrink` to make items shrink at a higher rate. 

##### mozilla on flex-shrink
Where the `flex-grow` property deals with adding space in the main axis, the `flex-shrink` property controls how it is taken away. If we do not have enough space in the container to lay out our items, and `flex-shrink` is set to a positive integer, then the item can become smaller than the `flex-basis`. As with `flex-grow`, different values can be assigned in order to cause one item to shrink faster than others — an item with a higher value set for `flex-shrink` will shrink faster than its siblings that have lower values.

The minimum size of the item will be taken into account while working out the actual amount of shrinkage that will happen, which means that flex-shrink has the potential to appear less consistent than flex-grow in behavior. We’ll therefore take a more detailed look at how this algorithm works in the article [Controlling Ratios of items along the main axis](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout/Controlling_Ratios_of_Flex_Items_Along_the_Main_Ax).

### flex-basis

`flex-basis` sets the initial size of the item. Any sort of `flex-grow`ing or `flex-shrink`ing starts from that baseline size. 
With a value of `auto` the item will take up what the space that the contents need.

Using `auto` as a flex-basis tells the item to check for a width declaration of the flex items.

##### mozilla on flex-basis
The `flex-basis` is what defines the size of that item in terms of the space it leaves as available space. The initial value of this property is `auto` — in this case the browser looks to see if the items have a size. In the example above, all of the items have a width of 100 pixels and so this is used as the `flex-basis`.

If the items don’t have a size then the content's size is used as the flex-basis. This is why when we just declare `display: flex` on the parent to create flex items, the items all move into a row and take only as much space as they need to display their contents.

#unsure
### flex in practice
Generally, you’re most likely to use declarations like `flex: 1;` to make divs grow evenly and `flex-shrink: 0` to keep certain divs from shrinking.

If we have three 100 pixel-wide items in a container which is 500 pixels wide, then the space we need to lay out our items is 300 pixels. This leaves 200 pixels of available space. If we don’t change the initial values then flexbox will put that space after the last item.


### Axes
The default direction for a flex container is horizontal, or `row` but you can change the direction to vertical, or `column`.

Specifying direction: 
<pre>.flex-container {
	flex-direction: column;
}</pre>

Possible values: 
- `row`
- `row-reverse`
- `column`
- `column-reverse`


### Alignment
`justify-content` aligns the items inside a flex container across the *main axis*.
Values accepted are 
- `center`: centers all items in a cluster in the middle of the container
- `space-between`: places the items with even space *between* them

`align-items` aligns the items along the *cross-axis*

When the `flex-direction` is changed, then the behaviour of `justify-content` and `align-items` changes, because they're based on the main and cross axis.

### Gap
`gap` adds a specified space between flex-items, similar to margins. 


### Other flex arguments
- `flex-wrap` allows the flex items to wrap to new lines when needed.
Values: `wrap` & `nowrap`
- `flex-flow` shorthand that combines `flex-direction` and `flex-wrap`: `flex-flow: flex-direction flex-wrap;`




