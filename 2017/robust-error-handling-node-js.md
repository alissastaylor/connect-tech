Robust Error Handling with Node.js
Thurs 02:20 PM
Lewis Ellis
Slides at github.com/LewisJEllis/node-error-talk
https://www,joyent.com/mode-js/production/design/errors
https://nodejs.org/api/errors.html

#Why should we want robust error handling in Node?
  *'This should never happen' famous last words

#How node is different
  *can handle multiple requests at the same time in the same thread
  *we could end up in situations that we have to restarrt our program altogether to get back to a good state
  *Error in JS: Special class
    *do not throw anything other than an error object

#Three Guiding Principles
  1. Always know when errors happen
    -empty error functions are worse than doing nothing

  2. Handling what we can and avoiding what we can't

      -Operational errors: Something that goes wrong in our system that could have been predicted, and recovered
        *At least have an error page or code to come out. 
        *Recoverable if we handle them correctly
        -Don't trust the outside world too much
        -full disk
        -S3 goes down
        -Database is down
        -Network Timeouts

      -Program Error: You made an error in your code
        *global error to fix the issue
        *Use Linter (ex: jshint) to help you avoid programming errors

  3. Don't keep running in unknown state
    -This could cause memory leaks, infinite loops, etc
    -If this happens, bail out and restart

  #The Game Plan
    *have a catchall for other team's bugs 
    *Use a process manager to help with shutting down

    1. Error Mechanisims in Node
    *core libraries have error handling mechanisims 

    Callbacks and try-catch
      - Pass errors to the callback, don't let errors bubble all the way up to the top
      - EventEmitters - listen for your error events
      - Express - can pass the error to the next callback
        - function (req, res, next, error) {
            //spit out the error, log the error, etc
          }

    2. Have a catchall for things we can't handle.

    3. Use a process manager to handle shutdowns
    -run multiple processes so if one shuts down you can still run processes
    -Node cluster module

    4. Do things nicely in case things shut down
    - Stop allowing new connections
    - Shut down any open resources
    - Tell process manager we are going to shut down
    - Use timeouts, or if/else statements to check if it happens multiple times
    - Shut down 

    -Use a stack trace to see the error
    - report operational errors to report operational errors
    - Sentry (Raven)

    -What NOT to do:
      - Do not keep the process running indefinitely
        - can cause mismatched users or state
      - Try to centuralize all the errors in one place
    
    -Other global error mechanisims
      - In the future: warnings will be changing to fatal 
      - Domains: Do not use if possible application code should not need them
        -async_hooks: lets us have runtime hooks into all async operations
      






