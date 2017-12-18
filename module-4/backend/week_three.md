 ## Week Three - Module 4 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week. 

Note: When you're done, submit a PR. 

1. At a high level, what is Node?

  Node is an environment that allows us to run JavaScript code outside of the browser. We use Node.js to create backend applications with JavaScript.

2. What is Express? What is Express similar to in the Ruby world?

  Express is a framework built on Node.js that we use to create server-side applications in JavaScript. It is very light-weight and unopinionated, which makes it similar to Sinatra.

3. How do we setup a route when creating an API with Node and Express? Please provide a code snippet.

  Without refactoring:

  ```javascript
  app.get('/api/v1/tasks', function(request, response) {
    response.send('Super Cool Server Response')
  })
  ```

  In a properly refactored MVC structure:

  ```javascript
  app.get('/api/v1/tasks', Tasks.index)
  ```

4. What do we use Knex for?

  Knex is a library we use to generate SQL queries in Node.js apps. We can create migrations, seed, and query.

5. How **could** you organize your code to follow the MVC design pattern in your Quantified Self project?

  Routes in the server.js file. request/response handling in controllers. knex SQL queries and other logic in the models.

6. How do you execute raw SQL in node?

  Knex provides us with a `.raw()` method. We can pass raw SQL into this method and execute that query.

7. What are some advantages to having your front end and back end code live in separate applications? What are some disadvantages?

  Separating the front end from the back end makes it easier to change things in the future. For example, if we wanted to update the front end to a more modern technology, we would not have to rebuild the backend. Additionally, we can serve multiple front-end applications from one back end, and vice-versa. It helps to organize at a very high level. However, creating separate applications can be time consuming, and it can be difficult to build out one half of an application without necessarily having the other half.

#### Review  

8. Describe DNS.

  DNS stands for Domain Name Server. DNS servers take the name of given domain, like www.google.com, and find its unique IP address. It can then direct me to the correct address.  

9. What does writing clean code mean to you?

  Clean code means a few different things:

  * Readable code - a developer that has not written my code can understand what I have done with as little struggle as possible.
  * DRY - Repeated logic is refactored into re-usable code.
  * SRP - Each module/class/object is responsible for one thing (or pretty close to one thing, contextually) - Practically, this generally means breaking logic apart into small chunks that fit together to provide broader functionality.

10. If you were building an application that models hotels, what classes would you need? What classes would be responsible for what functionality? Hint: think about what tables you would need in the database, how those records would relate to each other, and good OOP.

  * Guests - probably belongs to Hotels (One to Many), though this could be a many to many as well. Has many Reservations
  * Hotels - have many Guests, Rooms, Employees
  * Rooms - belongs to Hotel
  * Employees - belongs to Hotel
  * Reservations - Would join a many to many relationship between rooms and guests.
