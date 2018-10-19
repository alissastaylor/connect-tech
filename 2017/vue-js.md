Get More Done with Vue.js
Thurs 11:10 AM
Jonathan Kemp @jonkemp
Slides at speakerdeck.com/jonkemp


#Vue is very lightweight.
To use: create a js page and a html page.

Components:
  -With components the data is not mapped directly to the object
  -In vue components it's props down, views up
  -Vue.component('todo-item,' {
    props: increment
  })

How does the simplicity compare to other frameworks?
  -Angular needs typescript
  - React uses JSX
    -it can be used without JSX, but to learn that it is overcomplicated
    -ES2015+ (not required, but React documentation is written with it)
  -Both need a build system
  -Vue does not require a compiler
  -Anyone can start with ES2015+

Vue's Inspiration
  - Vue takes queues from other popular frameworks

Flexability
  -Not just limited to components with HTML and JS, can use vue-loader 
  -Can also use typescript
  -Can use render functions 
  -Can use JSX
    -very similar to react with/without jsx

Single File Components (All on one page)
  -<template></template>
    <script></script>
    <style></style>
  -complied with webpack

Compilers
  -Pug
  -babel
  -stylus
  -typescript
  -SCSS
  -PostCSS

Server-side Rendering
  -NUXT.js
    -similar to next.js in React

Mobile Development
  -Weex (newer project)
    -create native mobile ui components in native JS

Animation
  -can integrate third party css animations or js animations
  -can automatically use classes for animations

Extend Vue 
  -custom directives
  -mixins

Vuejs/Vue-router
  -official supported routing library 

State Management 
  -Vuex 
    -inspired by elm
  
Limitations
  -Cannot detect property addition or deletions

Performance 
  -How fast apps load
  -How fast it responds to our interactions

  Size
    -Vue is 23k g-zipped
    -Pre-compiling templates
      -help page render faster 
    -Async Components
      -render component only when used 
    -Server-side rendering 
    -Prerendering
    -Comparing with React
      -lighter-weight and faster
      -Improved render performance in Vue
        -react uses should component update
        -in Vue components are tracked and it knows which components should rerender

Vue Developer Tools
  -VueJs/Vue-cli
    -Allows you to structure the code however you want
  -Webpack
    -Webpack Loaders
      -allow you to preprocess files
      -vue-loader
      -webpack-simple

Prerendering
  -generates static html files from a static application
  -prerender-spa-plugin

Other Build Tools
  -Vueify
  -Rollup
    -support for vue components

Community 
  -Plenty of support
  -DevTools
  -Official ve.js form
  -Github
  -Awesome-vue
