## Week One - Module 4 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR.

1. What's the most useful thing you learned from completing the intermission week work?
How to import files, the testing basics was useful, introduction to debugging

2. What are some tools to help debug JavaScript code?
Debugger, console, source, inspect

3. What are some tools you need in order to unit test your JavaScript?
Mocha and the chai library

4. What is the syntax for invoking a function?
The name of the function with parentheses afterwards, like:  functionName()

5. What's `this` in JavaScript?
Depends on the scope within which it is used, but generally it refers to context in which a function is invoked. For example, when referenced in the global scope, it refers to the global object (the window). If inside of a function, it usually would refer to the object on which the function it's used in is called.

6. What is Webpack and why is it useful? Webpack is basically the asset precompiler for JS. It minifies, concatenates, etc., and then gets all of that information to one master(manifest?) file, which the page then loads. It's useful so that you don't have to manually import every file into that master file. It's also faster, because minified and concatenated files are more computer-efficient.

7. When/why do you want to use event delegation? Event delegation triggers by default, in the sense that every parent to an element with an event listener will "hear" the event unless you intentionally prevent that from happening (which you generally shouldn't do). I think its purpose is that you can just use one event listener but can trigger multiple events in different parts of the DOM.

8. What's `npm` and what do we use it for? node package manager. It's a... package manager--it manages JS packages the way that rbenv or rvm manages gems in rails.

#### Review  
9. What's the MVC design pattern? Describe each part of MVC.
Model View Controller--the view is what is returned to the user and the interface with which the user interacts with the application.  The view sends user input to the controller, which then directs the user's request appropriately through the model, which executes the logic and database interaction. The model then returns the resources that the user requested back through the controller, which then renders the appropriate view.

10. What are a few ways to optimize a Rails application? Caching, background workers, database refactoring (like using ActiveRecord instead of straight Ruby), CDNs to serve static assets, and using tools like NewRelic to locate and address bottlenecks (using one of the other above tools)

11. What's a background worker? When would we want to use a background worker? A background worker essentially takes certain tasks that don't need to be executed immediately and/or tasks that take more time to execute (like API calls, sending emails, generating shipping labels, charging credit cards, etc.) and offloads them to a service that runs in the background. That way, the user can continue to interact with the application as the longer job processes.
