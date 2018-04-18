## Questions

1. When this code is run in Node, e.g. node index.js, what are the two stages of execution for this file called, and which order do they happen in?

    ***Answer:*** *Hoisting/compilation and interpretation/execution*

2. Write an explanation, using as much space as you need, relating to how the first stage of execution for this file operates.

    - For example, identify the high level steps in a line by line overview and then define what each of those steps are accomplishing.

    ***Answer:*** *For the compilation phase, the engine moves through the code, finds all variable and function declarations, and keeps them in mind by hoisting them to the top of the code to be used during the execution phase. var foo and function bar() are hoisted in this file.*

3. Write an explanation, using as much space as you need, relating to how the second stage of execution for this file operates.

    - For example, identify the high level steps in a line by line overview and then define what each of those steps are accomplishing.

    ***Answer:*** *In execution, the engine then executes the code. It assigns values to the variables that were discovered during the compilation phase, and executes functions that were found in the same way. Execution for this file begins with assigning foo a value of 'bar', calling bar(), and so on.* 

4. During the second stage of execution how many scopes have been registered by the engine?

    - Which segments of the code do they belong to?
    - Please identify any variables/refs and which scope each belongs to?

    ***Answer:*** *There are three different scopes in this code - global, bar(), and baz(). Global scope encompasses the entire file and includes the variable foo and the function bar. In bar's scope, foo is reassigned a value and baz also exists within this scope. Baz has its own scope in which two variables are reassigned values.*

5. When line 13 invokes the baz function, which foo will be assigned a value of bam? More specifically, bam will be assigned to the foo in ??? scope. Give a brief description in your own words to support your conclusion.

    ***Answer:*** *When the function baz is invoked, foo is not able to be reassigned because it was not called with an argument.*

6. Which scope, if any, will the variable bam on line 11 be registered to when the first stage of execution occurs on this file? Provide a brief description in your own words to support your conclusion.

    ***Answer:*** *This is not declared as a variable and is therefore not hoisted during the compilation phase. During execution when this line is encountered, the engine tries to find a variable bam to assign a value to but fails because the variable does not exist, and a reference error is thrown.*

7. For each line, 16 through 19, what is the return value for each?

    ***Answer:***

    *bar(); - reference error, cannot find variable bam*


    *foo; - returns 'bar' when called without any other calls that throw a reference error*


    *bam; - reference error, cannot find variable bam*


    *baz(); - reference error, cannot find function baz*