## Week Three Recap

### Instructions
Fork this repository. Be sure to pull the latest changes to your local repo. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Questions

1. What is the entry at the command line to create a new rails app?

  `rails new <FILENAME> <OPTION-TAGS>`

2. What do Models generally inherit from in rails?

  `ApplicationRecord`

3. What do Controllers generally inherit from in a rails project?

  `ApplicationController`

4. How would I create a route if I wanted to see a specific horse in my routes fitle assuming I'm sticking to standard conventions and that I didn't want other CRUD functionality?

  ```ruby
  resources :horses, only: [:show]
  ```

5. What rake task is useful when looking at routes, and what information does it give you?

  `rake routes`

  This gives a list of all available routes, per the config routes file. Specifically, for each route, you get the prefix, verb, URI pattern, and controller#action.

6. What is an example of a route helper? When would you use them?

  The route in question 4 would give us the route helper, `horse_path`. A new horse route would be `new_horse_path`. Route helpers are used whenever we want to specify a URI in general terms(controller redirects, view links, testing expected paths, etc.)

7. What's the difference between what `_url` and `_path` return when combined with a routes prefix?

  Using `_path` returns the url relative to the domain of the rails app, while `_url` returns the entire http address. For example, `horses_path` would return `/horses` while `horses_url` would return `http://railsapp/horses`.

8. What are strong params and why are the necessary?

  You can use strong params by replacing `params[:something]` with `params.require(:something).permit(somethingsattribute)`. This is much more secure as assignment of non-permitted attributes will fail.

9. What role does `form_for` play in helping us create our forms?

  `form_for` is used to select the model on which the form will be acting. It simplifies the form creation process by acting as a sort of shorthand.

10. How does `form_for` know where to submit the user's input?

  By passing an instance variable from the associated model method.

11. Create a form using a `form_for` helper to create a new `Horse`.

  ```
  <%= form_for @horse do |f| %>
    <%= f.label :name %>
    <%= f.text_field :name %>

    <%= f.label :age %>
    <%= f.text_field :age %>

    <%= f.submit %>
  <% end %>
  ```

12. Why do we want to validate our models?

  To make sure incomplete or duplicate records can not be created. For example, a horse from the form in question 11 without a name or age would be near useless for us. Validations ensure all horses created have the desired attributes and relationships.
