Tame the Async Redux Beast with redux-logic
Friday 1:00 PM
Ray Gesualdo
raygesualdo.com


#Async Redux
  - Redux - library for maintaining application state
    - does this by holding state in JS in a store
    - If you want to change anything, you send an update (dispatch), then describe what you want to do with an action
    - Reducer functions take the action, change the state, and apply that change
    - This is all sychronous
    - Reducer functions are meant to be pure. Pure - given a specific input, you will always get the same output
  
#Where do things like hitting an API, websockets, or setting a timeout fit into being sychronous?
  - Side effects - anything that breaks out of that "pure" flow

#Criteria
  #Must Haves
    - Low barrier of entry
    - flexible 
  #Nice to have 
    - Declarative configuration
    - Little to no boilerplate
  
  #Lay of the land
    #Thunk - instead of dispatching an action, dispatch a promise, wait, then send to the store
      - Work well at low complexity (needed higher complexity)
      - Low Barrier of entry
      - required boilerplate
    #Redux sagas - 
      - Did not have low barrier of entry
      - High flexability
      - Too much boilerplate
    #Redux observables (RxJs) - 
      - Pretty steep learning curve, esp if you aren't familiar with observables
      - very flexible 
      - Decently declarative
      - Low boilerplate
    #Write your own
      - would rather use a well-tested, solid library 

  #Redux Logic 
    - https://github.com/jeffbski/redux-logic
    - Built ontop of RxJs, but does not require you to know observables
    - Lets you write your code however you like
      - Promises
    - Flexability
    - very declarative with config
    - very low boilerplate
    - Lets you declaritively configure things like: 
      - throtting 
      - dispatching
    - Dependancy injection
  
  #Setup
    - import {createStore, applyMiddleware} from 'redux'
    - import reducers from './reducers'
      -use combine reducers to build out your state tree
    - import { createLogicMiddleware } from 'redux-logic'
    - import logic fom './logic'
    - import api from './api'
      -imagine this is all promise-based 
        -fetch
        -axios
    - const logicMiddleware = createLocicMiddleware(logic, { api })
    - const store = createStore(
        reducers,
        {},
        applyMiddleware(logicMiddleware)
      )
  
  #Transform Validate Process
    #Transform happens before actions hit reducer
      - import { createlogic } from 'redux-logic'
      - import uuid from 'uuid'
        -if dependancy is only going to be used on one page, import it on the page
      - Export const addNorificationLogic - createLogic(())
      - Transform function get 2 params:
        1. transform({ action },
        2. next) {}

    #Validate happens after the store is updated
      - 3 params
        1. action, api
        2. accept
        3. reject
        - can also send action to provide message to users if things don't work or go as planned
  
  #Async Await 
    - import { creatLogic } from 'redux-logic'
    - import actions from './actions'
    - latest: true,
      - if it's working on a login action, it's going to drop the previous action and begin working on the next
      - Only take the latest one
    - async process({ action, api, history }), dispatch, done 
      - three dependencies 
        - action (same as above)
        - dispatch - allows you to dispatch multiple actions
        - Done - lets Redux logic know the code is done, and it doesn't have to use it anymore
    - Once login has happened
      - get webtoken from API
        -save in local storage
      - login sucessfully
      - history.push to homepage
    -if there is an error: 
      -catch(error)
    -Once everything is done, call done()

  #Promises (using a search)
    - Filter on the type we want to use
    - Latest is still true
    - debounce: 500
      - similar to throttling
      - makes sure we are not making too many connections at once
    - processOptions 
      - autodispatching - smart enough to be handed a promise and know if it succeeds it gives it a success and runs X, but if it rejects it gives it a failure and run Y
    - Promise allows search results to go all the way to the top
      -don't have to use .then or .catch dispatch
    - Not setting local storage
    - Not doing history.push

  #More to Learn
    - Multiple action types and type RegEx
    - Throttling 
    - Observables
    - Dispatching multiple times
    - Adding/merging/replacing logic at runtime
    - Add dependanceies at runtime
      - can wait until someone is on a certain route and can have the dependency loaded then
    - Testing 
      - Helps mock your store and dependencies for you
    






