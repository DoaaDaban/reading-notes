# Read10

## JS

### Error Handling & Debugging

#### I learned from this chapter:

1. the order of execution in the code helps in the Debugging process
1. There is one global execution context; plus, each function creates a new new execution context.
1. Every statement in a script lives in one of three execution contexts:
   - global context
   - function context
   - eval context (not shown)
1. when a statement needs data from another function, it stacks the new function on top of the current task
1. Each time a script enters a new execution context, there are two phases of activity:
   - prepare
   - execute
1. UNDERSTANDING SCOPE
1. If a JavaScript statement generates an error, then it throws an exception.
1. Error objects can help you find where your mistakes are
1. JavaScript's seven different types of error objects
   - Syntax Error
   - ReferenceError
   - EvalError
   - URI Error
   - Type Error
   - RangeError
   - Error
   - NaN
1. How to deal with errors
1. narrow down where the problem might be makes the debugging process easier
1. The JavaScript console will tell you when there is a problem with a script
1. some console methods:
   - log
   - info
   - warn
   - error
   - group
   - groupEnd
   - table
   - assert
1. You can pause the execution of a script on any line using breakpoints.
1. If you know your code might fail, use try, catch, and finally. Each one is given its own code block
1. If you know something might cause a problem for your script, you can generate your own errors before the interpreter creates them.
1. some of the common errors
