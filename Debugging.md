# Debugging
So, what is debugging? Debugging is a multistep process of detecting and fixing ‘bugs’ or errors in code.
## Sections
1) [Types of Errors](<#Types of Errors>)
2) [Debugging Strategies](#Strategies)
3) [External Resources](<#External Resources>)
# Errors
1) [Compile-Time Errors](<##Compile-Time Errors>)
2) [Run-Time Errors](<##Run-Time Errors>)
3) [Logical Errors](<##Logical Errors>)
## Compile-Time Errors
**Compile-Time Errors** - Compile-Time Errors, also known as syntax errors, occur during the compilation of the Python source code before the program is executed. These errors result from violations of Python's syntax rules, making the code impossible to parse and compile. They must be fixed before the program can run.


## Run-Time Errors
**Run-Time Errors** - Run-Time Errors occur during the execution of a Python program. These errors are not detected until the program is running and actively performing operations. Run-time errors can be caused by various factors, such as incorrect data types, invalid operations, or issues related to the program's logic. They must be handled using error-handling techniques like try-except blocks.

Useful Techniques:
- [Test Driven Development](<##Test Driven Development>)
- [Debugger](<##Debugger>)

## Logical Errors
**Logical Errors** - A logical error, also known as a semantic error, is a type of programming error in which the code is syntactically correct and executes without raising any exceptions, but it does not produce the intended or correct result due to a flaw in the program's logic or algorithm. These errors are often subtle and require careful analysis to identify and correct because they stem from incorrect assumptions or flawed reasoning in the program's design.


Useful Techniques:
- [Test Driven Development](<##Test Driven Development>)
- [Debugger](<##Debugger>)

# Strategies
## Understanding a Stack Trace and Error Messages
Being able to read and understand a stack trace is a useful debugging technique because it gives context to the circumstances an error occurred under. For context, a stack trace displays an error message and tracks the error's occurrence through nested functions. It displays where the error occurred from the lowest level code to the highest level function at the that called this code. Whether the stack trace is in ascending or descending order depends on the language. However, is important to note not all languages have stack traces natively. 

## Test Driven Development
Approaching testing with a methodology is highly beneficial because testing is likely more than half of the work on a project. Test driven development is a method of writing code where you focus on writing tests for a feature first and then implementing that feature such that it passes those tests. This debugging method is extremely useful, especially when working on larger projects, because it helps you organize yourself and focus on small parts of the overall program at a time. It also ensures you identify features you accidentally break when modifying other parts of the program.

The general steps of test driven development are as follows:
1. Select feature
2. Write test
3. Run test
4. Minimum amount of code to succeed
5. Run test again
6. Refactor
7. Move on to next feature

### 1) Feature Selection
The first step of test driven development is to select the feature you want to develop. In order to select your feature, it is a good idea to break down your overall problem/program into atomic sub-problems you can easily test and implement. For your own benefit, breaking down the problem is important so you can remain focused on implementing the feature instead of potentially getting lost trying to both understand the problem and create you implementation.
## 2) Write Test
Next, you will write a test. When writing a test you will make sure If it is difficult to write a test for the feature you are working on, you likely did not break it down enough.
### 3) Run Test
After writing your test, make sure to run it even though you have not implemented anything. Despite this seeming unnecessary, ensures your test fails properly when nothing is written.
### 4) Write the Minimum Amount of Code for Success
Then you will write the minimum amount of code for success. You write the minimal amount of code for you test case to pass so you can effectively get a working "rough draft" of that feature. This prevents you from wasting time keeping other requirements in mind that may be easier to accomplish later in the process.
### 5) Run Test Again
Now you will run your test again and see if it passes. If it does not work, revisit the previous step and keep trying.
### 6) Refactor Code
Once you have a working feature/function, refactoring (revising) your code is the next step. You will want to remove any duplicate code you wrote. It is a good idea to move this into its own function since you have proven that you will need it multiple times. You should also revise any code that is weird or difficult to read and understand due to its structure.
### 7) Repeat for Next Feature
Once you get to this step, select another feature and repeat the process.
## Print Statements
Print statements can be inserted at various points in your code to track down where it is failing and what values variables are taking. It is a good idea, to include a variable at the top of your program that indicates whether you want debug output like `DEBUG` that takes a Boolean value. You will then want to enclose the print statements in an if statement such that they only execute when `DEBUG` is true. If you are using C or C++, you can use preprocessor directives which can completely remove debug code so it does not get compiled when `DEBUG` is false.
## Debugger
### Breakpoints
Breakpoints are temporary markers that you place in your executable program to tell the debugger to stop your program at a given point.

When the debugger encounters a breakpoint, the debugger suspends execution at the breakpoint before it executes the statement. At this point, you can you can see the stack for the thread and check the contents of variables, registers, and memory. Then, you can step over (execute) the statement and see what effect it has on the argument.

When compared to [print statements](<#Print Statements>), this method is advantageous because your debugger will likely show you all variable values, not just the ones you selected, possibly revealing errors you did not catch with print statements since with print statements you have to explicitly identify the variables you want to get the values of.
### Variable Inspection
Variable Inspection is the process of examining the values and states of variables within a computer program while it's running or during a debugging session. 

It allows developers to track and analyze how the values of variables change as the program executes, helping to identify and diagnose issues, such as bugs or unexpected behavior. 

## Rubber Duck Debugging
Rubber duck debugging is a method of debugging where you walk through your code explain it to a rubber duck like you would another person (pretending to explain it to a rubber duck will suffice). 

This technique allows you to get a better understanding of your code and look at it through fresh eyes. It can be especially beneficial to write out what your code should do and how variables should change because it will be easier to identify any discrepancies between the expected and actual behavior of your code.

# External Resources
Additional resources for debugging:
- [Python Tutor](https://pythontutor.com/) is a online compiler and debugger that supports Python, Java, C, C++, and JavaScript. It is useful to step through relatively short pieces code and see how they work. Python Tutor is especially helpful for understanding concepts like recursion.