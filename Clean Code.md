My tips and takeaways from "Clean Code" by Robert C. Martin



### VARIABLES
- use meaningful and pronounceable variable names
- use named numbers as CONST in caps
- use searchable names
- use variables as arguments to a function (if it is not a variable, create a variable and pass it as an argument)
- use explanatory varibles instead of (i, l, j, k...)
- dont add unneeded context (if your class/object name tells you something, don't repeat that in your variable name)
- use default arguments inside the `function f(def = "deff") {}`


### FUNCTIONS
- functions should do one thing!!!
- use 2 or fewer function arguments. create an option if you need more
- function names should say what they do
- functions should only be one level of abstraction (split helper functions out of the main function; will make it easier to test )
- remove duplicate code. there should not be more than one place to alter something if you need to change some logic
- set default objects with Object.assign
- don't use flags as function parameters; instead split out the functions if they are following different code paths based on a bollean
- avoid side effects in your code. (eg of side effects: writing to a file, modifying global variables, modifying other variables like pushing to an array) IF you do have it, centralize where these type of side-effect functions are written.
- do not write to global functions
- favor functional programming over imperative programming (use .map .reduce instead of for-loops)
- encapsulate conditionals (create additional functions that return booleans based on conditionals)
- avoid negative conditionals
- avoid conditionals and use classes to manage it
- do NOT over-optimize as browsers do a lot of optimizations under the hood at runtime.
- remove dead code (backups are still in the commits)


### OBJECTS && DATA-STRUCTURES
- use getters and setters
- make objects have private members


### CLASSES
- prefer ES6 classes over ES5 constructor function
- use method chaining (try to return 'this' at the end of every function)


### ERRORS
- throw errors and then call other functions to handle errors like, notifyUserOfError(err) and reportErrorToService(err)


### FORMATTING
- use consistent capitalization
- keep the caller function right above the called function


### COMMENTS
- only comment things that have business logic complexity
- don’t leave commented out code in your codebase
- avoid journaled comments
- avoid positional markers in your code
