## Week Four Recap

### Instructions
Fork this repository. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Questions

* What is a cookie?

	A cookie is information sent from a website and stored on a users computer/browser. That information allows us to deal with the fact that HTTP is otherwise stateless, and makes things like authentication possible.

* What’s the difference between a session and a cookie?

	Sessions are like cookies, in that they allow us to store information, but sessions are stored on the server side while cookies are stored on the client side.

* What’s a flash and when do you want to use flashes?

	flashes allow us to pass information between controller actions and are then cleared out. They are usefull for passing information to the user of the site, such as messages as to the success or failure of logic within controller actions.	

* Why do people say “HTTP is stateless”?

	HTTP is stateless because no information is stored by either the server or client. Essentially, each individual http request can be understood in isolation.

* What’s authentication? Explain.

	Authentication is the process of determining if a user exists and they are who they claim to be. On a website, this would take the form of checking a password or other identifying information against a database to ensure they match and procedures like login are possible.

* What’s the difference between authentication and authorization?

	While authentication deals with determining who someone is, authorization is about what that person has access to. For example authorization would determine that a user might have acces to his own profile but not the profiles of other users or admin controls.

* What’s a before filter?

	A before filter allows us to call a method before all or many controller actions are run. It is a way of refactoring and reducing repetition. 

* How do we keep track of a user once they’ve logged in?

	We use sessions. We create a session that identifies the current user on login and clear that session on log out.

* When do you want to namespace a resource? When do you want to nest a resource? What's the differences between those two approaches?

	Namespaceing allows us to create routes like user/items while the nested equivalent would be user/:id/items. Namespacing is thus really useful when we have a case where id is not important (like when building routes for an Admin user). It makes the routes more readable and helps keep things organized and specific.

* At a high level, what tools can you use to implement authorization? How would you use them?

	When i think about authorization, I think about controllers (specifically parent controllers) and methods that can be built and before_actioned to restrict/allow access. For example, a method 'current_user' placed on the ApplicationController can be used in child controllers and even views (viea helper_method designation) in concert with additional logic to drive web app behavior.

* What's an enum, and what advantages does it offer? What data type needs to be in your database to use an enum? Where do you declare an enum?

	enums allow us to simplify an attribute that might only have a few potential values and thus significant repetition. Attributes are saved in the database as integers (i.e. 0 for "user" and 1 for "admin") and are declared as such at the model level. Enums also grant us access to instance methods that make checking the attribute nice and easy.

* What are some strategies you can use to keep your views DRY?

	Remove as much logic as possible from the views. Declare methods at the model level that can be called by the controllers and used by the views.
