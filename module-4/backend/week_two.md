## Week Two - Module 4 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week. 

Note: When you're done, submit a PR. 

1. What's one difference between ES5 and ES6?

  * In ES5, variables are declared with `var`. IN ES6 they are declared with `let`.

2. What's the difference between asynchronous and synchronous JavaScript? 

  JavaScript is run synchronously. That is, one task must be completed for another one to start. However, the browser provides an API that allows for javascript code to be executed asynchonously, using a queue. 

3. What are the four pillars of Object Oriented programming?

  1. Inheritence
  2. Abstraction
  3. Encapsulation
  4. Polymorphism

4. What are some tools available in JavaScript to help you write object oriented code?

  In es6 we have the ability to created classes. Javascript also uses prototyping to allow method inheritence.

5. What are some key concepts to be aware of when refactoring your JavaScript?

  Name effectively, make things DRY and make sure code adheres to SRP.

6. What's a callback function and what are some reasons when we use/need callback functions?

  Callback functions are functions that are passed as parameters into other functions. The callback function is then called within that function.

7. What are the different scopes of variables in Javascript? When would you want to define global variables?

  In JavaScript, variables are either scoped globally or locally. Global variables are used when you want the value to be available globally, or to multiple functions. Local variables are local to the function they exist within, and should be used when variables are not needed outside of the given function context.

8. What's the difference between `==` and `===` in JavaScript?

  `===` is for strict equality. Values must be exactly the same for a true return. `==` is for abstract equality, and allows for conversion to common datatype. For example, `3 == "3"` returns true, while `3 === "3"` returns false.

9. Why do front end frameworks exist?

  Front end frameworks exist to allow us to make repetative or inefficient development much easier, by providing tools and structural convention.

#### Review  

10. Why do people say "HTTP is stateless"?

  Each request lives alone and is executed in isolation.  

11. Describe a RESTful API.

  A RESTful API will adhere to the convention of limiting actions to GET, POST, PUT/PATCH, DELETE.  

12. What are some main characteristics of a team following an agile workflow?

  Agile workflow uses sprints and has participants complete iterations. Each iteration is wholistically developed - that is, each chunk of work is competed in full (with testing, style, etc.), so that features and functionality are rolled out one piece at a time. This allows for flexiblity and compartmentalization.

13. What are some advantages **and** disadvantages to using OAuth to authenticate a user?

  Don't have to worry about authentication - someone has done it better than I can.
  Saves time/effort
  Can complicate the login process
  Can limit user-base to users of the oauth provider.
