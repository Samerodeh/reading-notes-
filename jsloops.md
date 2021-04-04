# JavaScript & jQuery 
## Comparison and logical operators

>Comparison operators 

* operators that compare values and return true or false. The operators include: >, <, >=, <=, ===, and !==.


>Logical operators 

* operators that combine multiple boolean expressions or values and provide a single boolean output. The operators include: &&, ||, and !. 

## for and while loops 

***Loops check a condition. If it returns true, a code block will run. Then the condition will be checked again and if it still returns true, the code block will run again. It repeats until the condition returns false. types of loops:***

>1. FOR 

**If you need to run code a specific number of times, use a for loop. (It is the most common loop.) In a for loop, the condition is usually a counter which is used to tell how many times the loop should run**

*The For Loop
The for loop has the following syntax:*


for (statement 1; statement 2; statement 3) {
  
  // code block to be executed

}


* *Example*

for (i = 0; i < 5; i++) {
  
  text += "The number is " + i + ("br");

}

>2. WHILE 

**If you do not know how many times the code should run, you can use a while loop. Here the condition can be something other than a counter, and the code will continue to loop for as long as the condition is true**

*The While Loop
The while loop loops through a block of code as long as a specified condition is true.*


* *Syntax*

while (condition) { 
    
// code block to be executed

}


* *Example*

while (i < 10) {
  
  text += "The number is " + i;
  i++;

}