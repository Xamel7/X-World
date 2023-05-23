## Functional Programming

# What is functional programming?
Functional programming is a programming paradigm — a style of building the structure and elements of computer programs — that treats computation as the evaluation of mathematical functions and avoids changing-state and mutable data

# What is a pure function and how do we know if something is a pure function?
A pure function is a function that always produces the same output for the same input and has no side effects. It means that the function's behavior is solely determined by its input, and it does not modify any external state or variables. A pure function is predictable and does not introduce hidden dependencies, making it easier to test, reason about, and parallelize.

# What are the benefits of a pure function?
Pure functions offer several benefits in programming, including predictability, testability, code clarity, and support for parallel computing. They always produce the same output for the same input, making their behavior predictable and facilitating debugging. Pure functions are easy to test since they have no side effects and rely solely on their input.

# What is immutability?
Unchanging over time or unable to be changed.
When data is immutable, its state cannot change after it’s created. If you want to change an immutable object, you can’t. Instead, you create a new object with the new value.

# What is Referential transparency?
Referential transparency is a property of expressions or functions where they can be replaced with their resulting values without impacting the program's behavior. It is closely related to pure functions, which exhibit referential transparency by producing the same output for the same input. This property simplifies program understanding, enables optimization and caching of results, supports code reuse and modularity, and facilitates parallelization. 


## Node JS Tutorial for Beginners #6 - Modules and require()

# What is a module?
A module is just essentially another javascript file.That's all it is.

# What does the word ‘require’ do?
When you use the 'require' statement in JavaScript, it allows you to bring in functionality from other modules or files, making them accessible and usable within the current module or file. It helps in modularizing code and promoting code reuse by breaking down a program into smaller, self-contained units.

# How do we bring another module into the file the we are working in?
A few ways such as import,module.export, or require
# What do we have to do to make a module available?
To make it available in other modules you would use the module.exports