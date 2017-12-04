## Week One - Module 4 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week. 

Note: When you're done, submit a PR. 

1. What's the most useful thing you learned from completing the intermission week work?

  So far, the areas I have found most valuable have been exploring function behavior (especially more complex behavior, higher order functions, etc.), the `this` keyword, and objects.

2. What are some tools to help debug JavaScript code?

  * console.log()
  * debugger
  * browser console/dev tools

3. What are some tools you need in order to unit test your JavaScript?

  * mocha
  * chai

4. What is the syntax for invoking a function? Give an example.

  To invoke a function, we use `()` appended to the end of the function's name, either empty or with one or more arguments:

  es6 named function expression:

  ```javascript
  const someFunc = () => {
    // do something
  }
  someFunc()
  ```

  function statement:

  ```javascript
  function someOtherFunc(arg1, arg2) {
    // do something else
  }
  someOtherFunc(thing, otherThing)
  ```

5. What's `this` in JavaScript?

  `this` refers to context of a function. By default, the `this` keyword refers to the global object. Within functions, the value of `this` depends on the nature of the function being called.

6. What is Webpack and why is it useful?

  Webpack bundles all your js, css, asset files, and dependencies. This means you only need one script tag in your html and you don't have to worry about tracking down dependency bugs in production.

7. When/why do you want to use event delegation?

  Event delegation allows us to add a single event listener that can handle elements might not yet exist. It utilizes bubbling to handle events at a higher level in the DOM than the event originator. This is useful when page content is dynamically rendered and a direct anchor event listener might not work.

8. What's `npm` and what do we use it for?

  `npm` is the package manager for javascript. We use `npm` to install packages and manage dependencies. 

#### Review  
9. What's the MVC design pattern? Describe each part of MVC.

  MVC stands for Model View Controller, and is a web-app design architecture.

  * The 'Model' is where we put most if not all application logic. This part of the web app is responsible for creation and manipulation of objects and database queries.
  * The 'View' is the way we present information to the client. In rails apps we usually use html erb files here.
  * The 'Controller' is the switch-board for a web-app. It directs traffic by taking client requests, pulling data from the model level and rendering views to be passed back to the client.

10. What are a few ways to optimize a Rails application?

  * Cacheing
  * Indexed tables
  * Background workers
  * ActiveRecord Optimization (consolidated queries, remove n+1 queries, etc.)

11. What's a background worker? When would we want to use a background worker?

  Background workers are a way to execute regular jobs and actions that might otherwise compromise site performance or hamper scalability. For example, an app that relies on api calls might be slow and user-hostile if it makes calls every time the user clicks, the retrieval of this data might be better achieved by a regular - say - nightly call to the api. We can also use background workers to send emails and perform other jobs that would otherwise cause excess server load.
