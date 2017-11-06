## Week Four Recap

### Instructions
Fork this repository. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Questions

* What is a cookie? Data stored by a web browser to keep track of a user's state

* What’s the difference between a session and a cookie? A session is server side, whereas a cookie is user-side. Data in cookies can be seen and manipulated by users, whereas data in sessions is more secure. I think sessions also only last as long as a web browser is open, and cookies can be set for a certain duration.

* What’s a flash and when do you want to use flashes? A message that pops up when some action is taken.  They're short term, and only stay in a session until the next request. We've mostly used them to verify the success or failure of some invisible action--e.g., creating/updating/deleting something in the database.

* Why do people say “HTTP is stateless”? Each HTTP request is basically a new thing to the server--it doesn't really matter who the user is or where the requests are coming from, so the only way to persist state--e.g. the user or his/her activity-- is through sessions and cookies.

* What’s authentication? Explain. It's basically the verification that a user is who they say they are, as denoted by their username and password.

* What’s the difference between authentication and authorization? Authentication is verifying that user has a certain identity, whereas authorization is more the idea of what that particular user has access to--e.g., an admin user, after having been identified as such, may have access to more views or CRUD capabilities than a default user, vs. an unregistered visitor.

* What’s a before filter? A method that runs before controller action/s--you can have it run before any controller action, or specify which ones by using the only: keyword. We've used it mostly to ensure that a user is logged in before displaying a page, or to verify that a user is an admin before displaying certain things.

* How do we keep track of a user once they’ve logged in?  Umm, not sure what question is going for. Maybe the current_user method? Is that what you mean? Or do you mean like sessions/cookies?

* When do you want to namespace a resource? When do you want to nest a resource? What's the differences between those two approaches? Namespace allows you to nest a route without having to relate the models.  It also gives you access to a new set of views--for example, you can have admin/schools index, or just a schools index, and they'd be separate controllers and views.

* At a high level, what tools can you use to implement authorization? How would you use them?  
  -enums: they take a number assigned at the database level and translates it into a string representing a role--e.g., 0 == default, 1 == admin, and so on. It's a little more dynamic as it supports a flexible number of roles, etc.
  -allow_instance_of: basically allows you to stub a test environment user as a current_user(logged in), so that you don't have to capybara fill everything out to log in every time you write a test. Cool stuff!
  -I think there's 5 total, but I left my notebook at school and can't remember the others.

* What's an enum, and what advantages does it offer? What data type needs to be in your database to use an enum? Where do you declare an enum? They take a number assigned at the database level and translates it into a string representing a role--e.g., 0 == default, 1 == admin, and so on. It's a little more dynamic as it supports a flexible number of roles, etc. So your user database table needs a column called role that takes an integer, and you would declare the enum in your user model.

* What are some strategies you can use to keep your views DRY? Partials.. that's all I can think of, really, although I'm sure there's lots more?
