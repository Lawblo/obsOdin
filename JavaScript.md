# JavaScript
- [[jsVariables]]
- [[jsOperators]]
- [[jsDataTypes]]
	- [[jsStrings]]
- [[jsConditionals]]
-  [[jsFunctions]]
-  [[jsArrays]]
-  [[jsLoops]]
-  [[jsDOM-Manipulation]]



JavaScript is written in [[HTML]] inside the `<script></script>` tags.

The `<script>` element should go into the head, and should include a `src` attribute containing the path to the JavaScript you want to load, and `defer`, which basically instructs the browser to load the JavaScript after the page has finished parsing the HTML. This is useful as it makes sure that the HTML is all loaded before the JavaScript runs, so that you don't get errors resulting from JavaScript trying to access an HTML element that doesn't exist on the page yet.


```HTML
<script src="my-js-file.js" defer></script>
```

Alternatively, the JavaScript can be included at the bottom of the HTML file, sp that it gets run after the [DOM](jsDOM-Manipulation) nodes are parsed and created 
 


