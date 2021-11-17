# jsLoops

A loop usually has one or more of the following features:

-   A **counter**, which is initialized with a certain value — this is the starting point of the loop.
-   A **condition**, which is a true/false test to determine whether the loop continues to run, or stops — usually when the counter reaches a certain value. 
-   An **iterator**, which generally increments the counter by a small amount on each successive loop until the condition is no longer `true`. 


## The For Loop
```JavaScript
for (initializer; condition; final-expression) {
  // code to run
}
```

its possible to run a for loop without the initializer, if the counter is defined at another point
```JavaScript
let i = 0;
for (; i < 10; i++) {
  // code to run
}
```
If the iterator is included in inside the for loop body, this can also be excluded:
```JavaScript
let i = 0;
for (; i < 10;) {
  // code to run
  alert(i++);
}
```
Everything can be removed, creating an infinite loop:
```JavaScript
for (;;) {
  // repeats without limits
}
```
## Exiting loops with break
The break statement can be used to exit a loop before all the iterations have been completed. 

## Skipping iterations with continue
The continue statement skips the next iteration of the loop. Instead of exiting the loop and going to the next code block, it skips whatever comes after the continue statement and starts the next loop iteration. 

## Labels for break/continue
Sometimes we need to break out from multiple nested loops at once.
We need a way to stop the process if the user cancels the input.

The ordinary `break` after `input` would only break the inner loop. That’s not sufficient – labels, come to the rescue!

A  *label* is an identifier with a colon before a loop:

```javascript
labelName: for (...) {
  ...
}
```


The `break <labelName>` statement in the loop below breaks out to the label:
```javascript
outer: for (let i = 0; i < 3; i++) {

  for (let j = 0; j < 3; j++) {

    let input = prompt(`Value at coords (${i},${j})`, '');

    // if an empty string or canceled, then break out of both loops
    if (!input) break outer; // (*)

    // do something with the value...
  }
}
alert('Done!');
```

In the code above, `break outer` looks upwards for the label named `outer` and breaks out of that loop.

So the control goes straight from `(*)` to `alert('Done!')`.

The `continue` directive can also be used with a label. In this case, code execution jumps to the next iteration of the labeled loop.

## while and do ... while loops
**while loop**
```JavaScript
initializer
while (condition) {
  // code to run

  final-expression
}
```
**do ... while loop**
```JavaScript
initializer
do {
  // code to run

  final-expression
} while (condition)
```

In a do..while loop the code inside the curly braces is always run once before the check is made to see if it should be executed again 

In while and for loops, the check comes first, so the code might never be executed.

## Which loop type should you use?
For, while and do...while are largely interchangeable. 