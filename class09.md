# Functional Programming Concepts

> ### What is functional programming ?

* **Functional programming is a programming paradigm, a style of building the structure and elements of computer programs, that treats computation as the evaluation of mathematical functions and avoids changing-state and mutable data** 

> ### What is a pure function and how do we know if something is a pure function ?

* **It is mean returns the same result if given the same arguments**  

*So how do we know if a function is pure or not ?*  

1. It returns the same result if given the same arguments (it is also referred as deterministic)

2. It does not cause any observable side effects 

> ### What are the benefits of a pure function ?

1. Given a parameter A → expect the function to return value B

2. Given a parameter C → expect the function to return value D 

> ### What is immutability ?

* **When data is immutable, its state cannot change after it’s created. If you want to change an immutable object, you can’t. Instead, you create a new object with the new value.** 

> ### What is Referential transparency ?

* **pure functions + immutable data = referential transparency**

# Node JS Tutorial for Beginners #6 - Modules and require()

> ### What is a module ?

* **module is just essentially another Javascript file** 

> ## What does the word ‘require’ do ?

* **It is required the other Javascript files** 

> ### How do we bring another module into the file the we are working in ?

* **required the module**

> ### What do we have to do to make a module available ?

* **Exports the module**

*For example :*

       Module.exports = file name (the files want it to be  available)

