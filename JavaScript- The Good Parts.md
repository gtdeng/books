#JavaScript - The Good Parts by Douglas Crockford

#BEST PRACTICES….DO's
-prefer coding practices that are error-proof by using consistent style.
-write easy to read code that is error-proof
-use triple equal signs instead of double equal sign
-declare all variables at the top of the function
-declare all functions before you call them
-use 'let' instead of 'var'! let=var that doesn’t hoist! Especially use 'let' inside for-loops
--better yet, use 'const' instead of 'let' and only use 'let' when you know the variable will change
-write global variables in ALL CAPS
-constructor functions should be named in IntialCaps and nothing else should be in InitialCaps
-always use curly braces so that you know which part of the code will run.  if (a) b() c() is actually if (a) {b()} c() instead of if (a) {b(); c()}
-always use 'else'….makes the code clearer and cleaner.
-use Douglas Crockford's JSLint (code quality tool, which tests whether you are using the bad parts of JS)
-write clean code instead of performance specific code (it is buggy). 
-use right curly brace to reduce errors (because if you use Left, JS will run Automatic SemiColon Insertion);
-IIFE style: use style#1 instead of style#2
--style#1: (function(arg){return}());
--style#2: (function(arg){return})();
--I will not use Crockford's recommended style because 'that' is used instead of 'this' in ECMA Scrip Polyfills. eg. 
Production steps of ECMA-262, Edition 5, 15.2.3.5
-use semicolons at the end of each statement, do not rely on Automatic SemiColon Insertion!


#BEST PRACTICES….DO's…from others (non DC)
-use ii over i, because searching for 'i' is a pain in a doc.


#BEST PRACTICES….DONT's
-avoid global variables (bad for reliability and security)
-avoid using 'switch' statements
-avoid the bad parts of JS.
-avoid 'new' keyword because it does things in the background you might not want. eval executes any code you give it (security issue).
-avoid using curly braces on the left instead of the right
--in most languages, it doesn’t matter where it is located, 
--but in JS, it might give you an error, so …
--use right curly brace to reduce errors (because if you use Left, JS will run Automatic SemiColon Insertion);
--
-do not write confusing code.
-don’t use '++' it causes errors so use 'i += 1'. ++ causes 'off-by-one error'
-don’t optimize early. optimize only when necessary; algorithm replacement is vastly more effective than code fiddling.
-don’t use 'with' statement because it is confusing and confusion can cause bugs!
-don’t be the exhibitionist and write 'clever' code!
-don’t use all subset of the language because there are bad parts of a language because the author can't fix it because it's release to the wild

------------------------------------------------------------------------------------------------------------------------------------------


#RATIONALE FOR GOOD STYLING
-Computers cant write programs with a set of requirements, but it can transcribe programs from one language to another language.
-Romans used to write in all upper case, no punctuation and no word breaks, causing a lot of confusion. Later they introduced lowercase, word breaks and punctuation that reduced the error rate!
-Good use of style can help reduce the occurrence of errors 
-Programs must communicate clearly to people.
-Object Keys must be strings caused by JS's Automatic Type Coercion.


#NUMBERS
-JS's Number type is not a 'int' but rather a 'double'
-million, billion, trillion, quadrillion.
-Numbers are first class objects
-
-The number that can be represented in JS is Number.MAX_VALUE = 1.7976931348623157e+308.
-Anything larger than Number.MAX_VALUE = Number.POSITIVE_INFINITY
-
-The Number that can be safely represented in JS is Number.MAX_SAFE_INTEGER = 9007199…
-Number over 9007199254740990 (9,007,199,254,740,990) (2^53) is undefined!
-Numbers less than 9 quadrillion is OK. 
-These include doubles and floats, numbers that have periods in them.


#OBJECTS
Object = aka Associative Array
-all Values are Objects except Undefined and Null.
-triple equals operator compares object references NOT values. it will return true only if they both point to the same object.
-'var obj = {c:c}' is the same as 'var obj = {c}' in ES6.


#FIRST CLASS OBJECTS:
-Properties include:::
--can be stored in a variable
--can be passed as a parameter
--can be returned from a function
--can be stored in an object
--can have methods
---eg Functions. Strings. Numbers. 


#NaN
-IS a special number. NaN is a number!
-is the result of undefined or erroneous operations
-is not equal to anything, including NaN


#CONVERTING Strings to Numbers and Vice Versa
-use Number fx, or + or parseInt.
-num = Number(str)
-num = +str;
-num = parseInt(str, 10);
--always include the second argument (the 10 radix)!
--
-use number's method or the String function
-str = num.toString();
-str = String(num);


#JARGONS:
-automatic semicolon insertion
-automatic type coercion


#FOR IN
-fails if an object has a 'hasOwnProperty' property
-don’t use it with an Array because it doesn’t guarantee the order.


#TO REMOVE AN ELEMENT IN AN ARRAY
-do not use delete array[number]
-because it leaves a hole in the numbering and insert 'undefined' into that number.
-use: array.splice(number, 1) instead!
-it removes all the elements and renumbers all the following elements.
-is slow! because it reindexes everything.


#BLOCK SCOPE vs FUNCTION SCOPE
-JS doesn’t have block scope, it has function scope!
-'var' statement gets split into two parts: declaration part and the assignment part.
--var myVar = undefined, THEN myVar = value


#QUOTES
-Douglas Crockford on being asked tricky/clever questions in JS.
--" I will find the guy who wrote that code and fire him"



#PRIVATE VARIABLES use "_privateVariable"
-use (underscore) to preceed private variables inside functions
-eg. _privateVar
--
-the use of an underscore prior to a variableName denotes that the variable is private for internal use only
-they should not be used outside of the class.
-they should not be read or written into (directly) from outside of the class
--you should create functions/methods to read/write to them
-is just a convention

