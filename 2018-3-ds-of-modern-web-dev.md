Three D’s of Modern Web Development (Declarative, Dependency Injection, and Data-binding)
Jeremy Likness
Thursday 10 am

# Declarative Syntax
  Imperative - code that explains how to do something (recipe for scrambled eggs)
  Declarative - describes how to do it (going to a resturant and asking for eggs)
  ## Why (and when) declarative
  - UI
  - Reusuable Behavior
  - Components
  - Metadata
  - Repeatible Code 
  - Bindings


# Dependency Injection
  How do we really have to change how we write our classes and code to resolve dependencies?
  Dependency Injection= - (SOLID Principles) - eliminates order requirements for mododules
  Inversion of Control (IoC) -  passing control of something outside of my function 
  Car 
    Engine
      Pistons
    Wheels
    Useful when having large projects where they only need to be configured once then can be cloned
    Useful for testing easy to mock dependencies for code

  # Data Binding
    View Model - manages the state that is being bound
    "The view is the responsibility of a designer rather than a classic developer" - John Grossman
    Model View ViewModel (MVVm)
    ## Benefits of Data-Binding
    - Develop and Design in Parallel
    - UI is Flexible
    - ViewModel is Testable
    - Less Responsibiliy for developer
    Modern JS frameworks support data-binding

#What's Next?
  If you fundamentally understand what is driving these frameworks, it will help you decide if you want to implement a new framework in the future. 