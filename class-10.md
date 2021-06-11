# JavaScript 

##  Chapter 10

### Error Handling & Debugging 

***When you are writing JavaScript, do not expect to write it perfectly the first time.
Programming is like problem solving: you are given a puzzle and not only do you have to solve
it, but you also need to create the instructions that allow the computer to solve it. too.***

***When writing a long script, nobody gets everything right in their first attempt. The error
messages that a browser gives look cryptic at first, but they can help you determine what
went wrong in your JavaScript and how to fix it.*** 

> EXECUTION CONTEXT

**Every statement in a script lives in one of three
execution contexts:** 

* GLOBAL CONTEXT

*Code that is in the script, but not in a function.
There is only one global context in any page.* 

* FUNCTION CONTEXT

*Code that is being run within a function.
Each function has its own function context.*

* EVAL CONTEXT (NOT SHOWN)

*Text is executed like code in an internal function
called eva l {).* 

> VARIABLE SCOPE 

* GLOBAL SCOPE 

*If a variable is declared outside a function, it can
be used anywhere because it has global scope.* 

* FUNCTION-LEVEL SCOPE 

*When a variable is declared within a function,
it can only be used within that function. This is
because it has function-level scope.* 


> The Stack 

**The JavaScript interpreter processes one line of code at a time when a statement needs data from another function, it stack or piles the new function on top of the current task** 

![Stack](https://miro.medium.com/max/1592/0*ryPdDzB_jghiVi2e.png)

> EXECUTION CONTEXT & HOISTING

**Each time a script enters a new execution context, there are two phases
of activity:** 

* PREPARE 

• The new scope is created

• Variables, functions, and arguments are created

• The value of the this keyword is determined

* EXECUTE 

• Now it can assign values to variables

• Reference functions and run their code

• Execute statements

> UNDERSTANDING SCOPE 

**In the interpreter, each execution context has its own va ri ables object.
It holds the variables, functions, and parameters available within it.
Each execution context can also access its parent's v a ri ables object.** 

> UNDERSTANDING ERRORS 

**If a JavaScript statement generates an error, then it throws an exception.
At that point, the interpreter stops and looks for exception-handling code.** 

> ERROR OBJECTS 

**Error objects can help you find where your mistakes are
and browsers have tools to help you read them.** 

> HOW TO DEAL WITH ERRORS

**Now that you know what an error is and how the browser treats them,
there are two things you can do with the errors:** 

* A DEBUGGING WORKFLOW

*Debugging is about deduction: eliminating potential causes of an error.* 

1. WHERE IS THE PROBLEM ? 

2. WHAT EXACTLY IS THE PROBLEM ?

> BROWSER DEV TOOLS & JAVASCRIPT CONSOLE

**The JavaScript console will tell you when there is a problem with a script,
where to look for the problem, and what kind of issue it seems to be.** 

**The JavaScript console is just one of severa l developer tools that are found in all modern browsers.** 

![console](https://i.stack.imgur.com/LvR0l.png)

> WRITING FROM THE SCRIPT TO THE CONSOLE

**Browsers that have a console have a console object, which has several
methods that your script can use to display data in the console.
The object is documented in the Console API.** 

> HANDLING EXCEPTIONS 

**If you know your code might fail, use try, catch, and finally.
Each one is given its own code block.**

![try, catch, and finally.](https://miro.medium.com/max/2440/1*dtzEohMaIfnKkB4luQGdEg.png) 

* TRY 

*specify the code
that you t hink might throw an
exception within the try block.* 

* CATCH 

*If the try code block throws an
exception, catch steps in with an
alternative set of code.* 

* FINALLY 

*The contents of the fi na 11 y
code block will run either
way - whether the try block
succeeded or failed.* 

