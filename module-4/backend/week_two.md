## Week Two - Module 4 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR.

1. What's one difference between ES5 and ES6?
ES6 supports classes. Also fat arrow syntax.

2. What's the difference between asynchronous and synchronous JavaScript?  Async: it doesn't flood the stack. When an async task is called within a function, if the stack isn't empty, it goes to the Web API, which then sends it to the event queue (after how long? does the web api immediately send the task to the event queue?). Once the stack is empty, the event loop will push the task from the queue to the stack. The benefit is that later tasks don't get backlogged behind that first task.

3. What are the four pillars of Object Oriented programming? Abstraction: most things are hidden under the hood for easier user interfacing.  Encapsulation: things that go together stay together in code. Inheritance: properties and behavior of a parent can be passed down to children.  Polymorphism: things that behave similarly even if they're different under the hood can have the same name.

4. What are some tools available in JavaScript to help you write object oriented code? Constructor functions, prototypes, classes in ES6, "extends"

5. What are some key concepts to be aware of when refactoring your JavaScript? File organization, DRYness, length of code, SRP

6. What's a callback function and what are some reasons when we use/need callback functions? A callback function is a function passed into another function as an argument. A lot of times it behaves like a block does in Ruby.

7. What are the different scopes of variables in Javascript? When would you want to define global variables? Global or local. Global can be seen by the whole file, local can be seen by the function that it's found within.  We've used them often with import statements, declaring global variables at the tops of files.

8. What's the difference between `==` and `===` in JavaScript? '==' does type coercion and '===' doesn't--for example, "2" == 2 would be true, but "2" === 2 would be false.

9. Why do front end frameworks exist? To give you tools to build applications, some assistance (to varying degrees--I'm looking at you, express!) with organization structure.

#### Review  

10. Why do people say "HTTP is stateless"? State doesn't persist between separate http requests. That's why we use cookies and sessions, to store that state manually between requests.

11. Describe a RESTful API. Certain http verbs correspond with certain actions and resource responses. For example, get corresponds to viewing a resource, post is to create, put/patch edit a resource, delete removes a resource. And within get, certain actions correspond to certain responses, such as an index returning a list, show returning a single resource, edit/new returning forms to edit or create.

12. What are some main characteristics of a team following an agile workflow? Sprints (tight feedback loops, iterative development), user stories, scrum process, retros

13. What are some advantages **and** disadvantages to using OAuth to authenticate a user? Advantages: easy, convenient for user. Disadvantage: developer loses control over login process within their own application.
