Effective React Testing
Jeremy Fairbank 
Friday, 10:00 AM
bit.ly/react-test-ct
github.com/jfairbank/effective-react-testing

#Testing Using Jest
- with Jest you can run specific tests without running all of them
- mount = fully renders everything 
- shallow = only renders the test results
- you can actually simulate click to test a callback

Using the function below better describes the function:
it('displays the title'), () => {
  const wrapper - shallow(<Album album={album} />)

  expect(wrapperfind('h1').text().toEqual('An Album'));
}


## This test uses containsMatchingElement to ONLY run tests on the defined parameter
expect(
  wrapper.containsMatchingElement(
    <img src="album.jpg"/>
  )
)



## This looks for anything that contains an album, it doesn't have to be a specific param (h1, h2 etc)
  expect(
    wrapper.contains('An Album').toBe(true)
  );



it('likes an album', () => {
  const onRate = () => {}
  const wrapper = shallow(<Album album={album} onRate={onRate} />)
  expect(
    wrapper.containsMatchingElement(
      <Like albumRating={albumRating}>
    )
  )
  )};


## Automating Component Testing
- renderer from 'React-testing-render' 
 - returns a json-like output for a component (Saves to a file)
 - This returns the static files that are actually rendered on the website
 - This updates the snapshot file each time instead of making a new one with each test


 ## Testing Redux
 - Test reducer, actions, and API library together
 - test Entire Application
 - More Setup
 it('receives albums', () => {
   const albums = [{}, {}]
   const result = reducer(initialState, actions.receivesAlbums(albums))
    expect(result.toEqual({
      ..state,
      albums: RemoteData.success([updatedAlbum, { id:2 }])
    }))
 })


##Testing the store
td.when(dependencies.api.all()).thenResolve(albums)
await action.loadAlbums()(dispatch, getState)
expect(store.dispatch(actions.loadAlbums())

beforeEach(() => {
  global.fetch - td.function(){ 

  }
})


## End to End testing
- Using Cypress.io
- Test entire application in browser
- Simulate user interactions
- Interact with real API
- Cypress takes snapshots 
- Test all pieces working together in user scenarios
- Cypress makes E2E pleaasant



