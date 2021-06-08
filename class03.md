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

***The spread operator is a useful and quick syntax for adding items to arrays, combining arrays or objects, and spreading an array out into a function’s arguments.***

### List 4 things that the spread operator can do.

* Copying an array

* Concatenating or combining arrays 

* Using Math functions

* Using an array as arguments

### Give an example of using the spread operator to combine two arrays. 


    const myArray = [`🤪`,`🐻`,`🎌`]
    const yourArray = [`🙂`,`🤗`,`🤩`]
    const ourArray = [...myArray,...yourArray]
    console.log(...ourArray) // 🤪 🐻 🎌 🙂 🤗 🤩



### Give an example of using the spread operator to add a new item to an array. 

    const fruits = ['🍏','🍊','🍌','🍉','🍍']
    const moreFruits = [...fruits];
    console.log(moreFruits) // Array(5) [ "🍏", "🍊", "🍌", "🍉", "🍍" ]
    fruits[0] = '🍑'
    console.log(...[...fruits,'...',...moreFruits]) //  🍑 🍊 🍌 🍉 🍍 ... 🍏 🍊 🍌 🍉 🍍

### Give an example of using the spread operator to combine two objects into one.


    [...["😋😛😜🤪😝"]] // Array [ "😋😛😜🤪😝" ]
    [..."🙂🙃😉😊😇🥰😍🤩!"] // Array(9) [ "🙂", "🙃", "😉", "😊", "😇", "🥰", "😍", "🤩", "!" ]

    const hello = {hello: "😋😛😜🤪😝"}
    const world = {world: "🙂🙃😉😊😇🥰😍🤩!"}

    const helloWorld = {...hello,...world}
    console.log(helloWorld) // Object { hello: "😋😛😜🤪😝", world: "🙂🙃😉😊😇🥰😍🤩!" } 

# How to Pass Functions Between Components 

### In the video, what is the first step that the developer does to pass functions between components? 

* ***creating a function***

### In your own words, what does the increment function do ?

* ***It is function modif the objects passing the objects, find the matching objects and update that***

### How can you pass a method from a parent component into a child component ? 

* ***write the method inside the render -> return component then call it where ever you want***

### How does the child component invoke a method that was passed to it from a parent component ? 

* ***write the method inside the render -> return component then call***