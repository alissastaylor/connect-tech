#Javascript Best Practices for Performance and Memory
Thurs. 01:10 PM
K. Devin McIntyre
https://speakerdeck.com/miyasudokoro/javascript-best-practices-for-performance-and-memory


#Causes of perform issues
  *DOM repaint and reflow
  *Inefficiencies at scale
  *Memory Issues

##Memory issues: Garbage Collection
  *Node: launch with --expose-gc and then use global.gc()
  *Studder can occur if you have too many animations or mouseover listeners

##Principles
  ###Make the smallest possible changes to objects
    *the less you do, the faster the object will go
    *to change style you should add/remove classes
  ###Keep references close
    *Dependency Injection: in reference to nested functions
      *Make each variable's access as limited as possible in a function
  ###DOM Mindfulness
  ###Finding a Balance
    *Focusing too much on performance can decrease productivity
    *Adding too many techniques can actually decrease confidence
    *Do not use a technique that is so advanced that only you can use it (because you put the time into learning it and no one else has done that)
    *Each situation is different. Things scale differently.
    *Pick a few options and stick with them. Use the techniques that are difficult sparingly.
  
  ##Techniques
    *Use small, simple functions that are pure if possible.
      *Reuse those functions
      *The larger the function the less likely it can be optimized
    *Defined classes in a function
      *Memory leaks can be found faster if there is a defined class with it
    *Auto-destruct
    *Bind
      *Allows you to use only what is needed for the function, nothing else. 
    *Limit Closures
      *Used if you don't want to use bind
    *Efficent CSS
      *Browser reads right to left
