1. How do we make flash messages display on a page?

	Within an action in the controller we can create a flash key value pair, for example `flash[:success] = "Good Job"`, which then persists through to the next action, before being cleared. I usually put the actual message call in the layout, so that the flash messaging works site-wide.

2. Where is cart information/temporary information usually stored?

	In a session.

3. What might be some reasons not to store cart in our database? Are there any reasons why we would want to persist that information?

	It would be wasteful as I'm sure some large percentage of visitors put things in their cart and then just leave the site without purchasing. It just seems like a temporary thing, and not something that should be persisted in a db. That said, I think it could be argued that having cart information in a db would allow for some interesting business anaylitics.

4. What is the purpose of the asset pipeline?

	The asset pipeline allows us to use javascript and css in an effecient way through compression and minification.

5. Why do we precompile our assets?

	To make things fast?

6. What do each of the following tags do?

```ruby 
<%= stylesheet_link_tag "application" %>
<%= javascript_include_tag "application" %>
<%= image_tag "rails.png" %>
```

	First tag links to the default rails css file called application.css
	Second tag links to the default rails js file called application.js

7. What are some of the elements of a great read me? What are some of the benefits of taking the time to update a readme for our project?

	* What the project is (why does it exist)
	* What the project does
	* Installation instructions (with detail)
	* Run/Deploy instructions (also with detail)
	* Contribution conventions
	* License
	* Authors
	* Version

8. What are the top four accessibility issues that we as developers should be aware of?

	1. Motor
	2. Visual
	3. Cognitive
	4. Auditory

9. `before_save` is an example of a what? Where in our Rails application would we find a `before_save`?

	`before_save` is a callback. A before_save would be in a model. (could this also be in a controller?)

10. Given the following object, how would we create a scope for all users who are active?

```ruby 
User.create(name: "Happy", active: true)
```
	At the model level:

```ruby
scope :active, where(active: true)
```

11. What is the difference between a scope and a class method?

	They are similar, but scopes can always be chained together while class methods might not (depending on the return value). Scopes also work with has_many relationships.
