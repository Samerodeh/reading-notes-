# React Docs - lists and keys

### What does .map() return ?

***return to the Components like :***

* variable 
* elements 
* numbers 
* values

### If I want to loop through an array and display each value in JSX, how do I do that in React ?

* ***we can do that by map function*** 

### Each list item needs a unique ____. 

* ***ID*** 

### What is the purpose of a key ?

* ***Keys help React identify which items have changed, are added, or are removed*** 

# The Spread Operator 

### What is the spread operator ?

***The spread operator is a useful and quick syntax for adding items to arrays, combining arrays or objects, and spreading an array out into a functionβs arguments.***

### List 4 things that the spread operator can do.

* Copying an array

* Concatenating or combining arrays 

* Using Math functions

* Using an array as arguments

### Give an example of using the spread operator to combine two arrays. 


    const myArray = [`π€ͺ`,`π»`,`π`]
    const yourArray = [`π`,`π€`,`π€©`]
    const ourArray = [...myArray,...yourArray]
    console.log(...ourArray) // π€ͺ π» π π π€ π€©



### Give an example of using the spread operator to add a new item to an array. 

    const fruits = ['π','π','π','π','π']
    const moreFruits = [...fruits];
    console.log(moreFruits) // Array(5) [ "π", "π", "π", "π", "π" ]
    fruits[0] = 'π'
    console.log(...[...fruits,'...',...moreFruits]) //  π π π π π ... π π π π π

### Give an example of using the spread operator to combine two objects into one.


    [...["ππππ€ͺπ"]] // Array [ "ππππ€ͺπ" ]
    [..."ππππππ₯°ππ€©!"] // Array(9) [ "π", "π", "π", "π", "π", "π₯°", "π", "π€©", "!" ]

    const hello = {hello: "ππππ€ͺπ"}
    const world = {world: "ππππππ₯°ππ€©!"}

    const helloWorld = {...hello,...world}
    console.log(helloWorld) // Object { hello: "ππππ€ͺπ", world: "ππππππ₯°ππ€©!" } 

# How to Pass Functions Between Components 

### In the video, what is the first step that the developer does to pass functions between components? 

* ***creating a function***

### In your own words, what does the increment function do ?

* ***It is function modif the objects passing the objects, find the matching objects and update that***

### How can you pass a method from a parent component into a child component ? 

* ***write the method inside the render -> return component then call it where ever you want***

### How does the child component invoke a method that was passed to it from a parent component ? 

* ***write the method inside the render -> return component then call***