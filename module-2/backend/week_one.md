## Week One - Module 2 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON!).

Note: When you're done, submit a PR.

1. List the five common HTTP verbs and what the purpose is of each verb.

  get - This is used to read a record
  post - Used to create a record
  put - Used to update a record
  patch - Also used to update a record??
  delete - Used to delete a record

2. What is Sinatra?

  Sinatra is a DSL that allows us to give Ruby apps a web interface in a lightweight way.

4. What is MVC?

  This is the model-view-controller structure that we use in Sinatra (and maybe Rails?) that is a sort of a way to maintain the spirit of single responsibility in our apps. We break things into a controller, model(s), and views.

5. Why do we follow conventions when creating our actions/path names in our Sinatra routes?

  I would imagine it is to make our lives (as programmers) easier and make it less likely for bugs and other errors to cripple apps.

6. What types of variables are accessible in our view templates without explicitly passing them?

  anything in the params.

7. Given the following block of code, how would I pass an instance variable `count` with a value of `1` to my `index.erb` template?

  ```ruby
  get '/horses' do
    @count = 1
    erb :index
  end
  ```

8. In the same code block, how would I pass a local variable `name` with a value of `Mr. Ed` to the view?

  ```ruby
  get '/horses' do
    @name = 'Mr. Ed'
    erb :index
  end
  ```

9. What's the purpose of ERB?

  ERB allows us to use ruby code within an html file.

10. Why do I need a development AND test database?

  The test database is not seeded and is cleaned constantly while the development database needs to be able to retain data so that you can play with it and still have a functioning app with a full database.

11. What's responsive design?

  I believe this is when we design web applications taking into account user device, screen-size, etc. Tools like bootstrap make this easier, for example.

12. What is CRUD and why is it important?

  CRUD stands for Create, Read, Update, and Destroy. This is important because it encapsulates just about everything a user needs to do in interacting with values in a database.

13. What does HTTP stand for?

  Hypertext Transfer Protocol

14. What are the two ways to interpolate Ruby in an ERB view template? What's the difference between these two ways?

  * `<% RUBY-CODE %>` - executes the ruby code within the tags
  * `<%= RUBY-CODE %>` - prints something into the erb file (that will then be visible on the page)

15. What's an ORM?

  An ORM is Object Relational Mapping. It is a way of using object oriented programming language to manipulate otherwise non-compatible or difficult data.

16. What's the most commonly used ORM in ruby (Sinatra & Rails)?

  ActiveRecord

17. Let's say we have an application with restaurants. There are seven verb + path combinations necessary to provide full CRUD functionality for our restaurant application. List each of the seven combinations, and explain what each is for.

  * get '/restaurants' - this allows the user to see all restaurants (Read)
  * get '/restaurants/:id' - allows the user to see a specific restaurant (Read)
  * get '/restaurants/new' - this provides the user with a form to create a new restaurant (Create)
  * post '/restaurants' - this creates the new restaurant and adds to the database (Create)
  * get '/restaurants/:id/edit' - this provides the user with a form to edit an existing restaurant (Update)
  * put '/restaurants/:id' - this updates the existing restaurant with new information (Update)
  * delete '/restaurants/:id' - this deletes an existing restaurant from the db (Delete)

18. What's a migration?

  I think of a migration as a sort of set of instructions for passing data into a database.

19. When you create a migration, does it automatically modify your database?

  No. You would need to run an actual migrate command.

20. How does a model relate to a database?

  A model is the piece of the MVC structure that actually queries the database based on requests from the controller.

21. What's the difference between agile workflow and waterfall method?

  Put simply, the agile workflow is all about taking small chunks one at a time and completing analysis, design, code, and test steps on those small chunks. The waterfall method is more traditional and involves applying the same steps but to the whole project at once.

22. What is the difference between `#new` and `#create`?

  * `#new` makes a new object but does not save it to the database
  * `#create` is actually two steps combined: `#new` and `#save`
