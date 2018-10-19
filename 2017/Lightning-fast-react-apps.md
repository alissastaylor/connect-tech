Lightning Fast React Apps
Friday 02:00 PM
Sia Karamalegos @thegreengreek

#Why should you care about performance
  - 53% of mobile sites are abandoned if pages take longer than 3 seconds to load
  - Concerned about loadtime and applications of the things we build
    

#Things you should always do
  #Use the production version of React in production
    - If using create react app
      - Dev -> npm start
      - Prod -> npm run build
  #Add keys
    - Iterators are not unique an stable
    - for each redefines the number each time. 
  #Always bind event handlers before render
    - Bind it in the class before the render function
    - Ex: handleClick = (e) => {
        //function component
      }
      render() {

      }
  #Never Mutate Objects 
    - immutable.js
    - reduce the chance for unwanted side effects
    - object.assign()


#Things you should only do if your app is too slow
  #Avoid reconciliation when unnecessary
    - Lifecycle method
    - shouldComponentUpdate()
      - ex: only update if color is not equal to the next color, or if count is not equal to the previous state
    - Pure component rather than the react component
      - react.PureComponent
        - Checks all props in all state, if nothing has changed it doesn't update

    

#React Performance add-on
  - Redux
    - Memorize any computed props in Redux mapStateToProps()
  - Reselect 

#More Speed
  - Server-side Rendering
    - next.js
