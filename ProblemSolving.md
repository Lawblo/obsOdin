# ProblemSolving

“Problem solving is writing an original program that performs a particular set of tasks and meets all stated constraints.” - Think Like a Programmer

**Understand the Problem**
The first step to solving a problem is to understand the problem.
**Plan**
The second step is to plan how you're going to solve the problem. 
- Questions you should answer at this stage:
	- Does your program have a user interface? What will it look like? What functionality will the interface have? Sketch this out on paper.
	- What inputs will your program have? Will the user enter data or will you get input from somewhere else?
	- What’s the desired output?
	- Given your inputs, what are the steps necessary to return the desired output?
 - **Pseudocode**
	 - Pseudo code is writing out the logic for your program in natural language instead of code. It helps you slow down and think through the steps your program will have to go through to solve the problem.
**Divide**
Break the problem into sub-problems. These sub-problems are much easier to solve. Then, solve each sub-problem one by one. Begin with the simplest. Simplest means you know the answer (or are closer to that answer).

**What to do when you're stuck?**
- Debug: Go step by step through your solution trying to find where you went wrong. Programmers call this _debugging_ (in fact, this is all a debugger does).
- Reassess: Take a step back. Look at the problem from another perspective. Is there anything that can be abstracted to a more general approach?
	- Sidenote: Another way of reassessing is starting anew. Delete everything and begin again with fresh eyes. I’m serious. You’ll be dumbfounded at how effective this is.
- Research: Ahh, good ol’ Google. You read that right. No matter what problem you have, someone has probably solved it. Find that person/ solution. In fact, do this even if you solved the problem! (You can learn a lot from other people’s solutions).


## [Tips for Resolving Errors

1.  Read the error _carefully_ and try to understand it on your own.
2.  Next, Google the error! Chances are, you can find a fix or explanation on StackOverflow or in the documentation. If nothing else, you will receive more clarity as to why you are receiving this error.
3.  Use the debugger! The debugger is great for more involved troubleshooting, and is a critical tool for a developer. You can set breakpoints, view the value of any given variable at any point in your application’s execution, step through code line by line, and more! It is an extremely valuable tool and every programmer should know how to use it. 
4.  Make use of the console! `console.log()` is a popular choice for quick debugging. For more involved troubleshooting, using the debugger might be more appropriate, but using `console.log()` is great for getting immediate feedback without needing to step through your functions. There are also other useful methods such as `console.table()`, `console.trace()`, and more! 