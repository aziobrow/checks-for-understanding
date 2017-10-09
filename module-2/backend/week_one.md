## Week One - Module 2 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON!).

Note: When you're done, submit a PR.

1. List the five common HTTP verbs and what the purpose is of each verb.
  -PUT: update entire resource
  -POST: create new resource
  -DELETE: destroy entire resource
  -GET: retrieve resource
  -PATCH: update part of a resource

2. What is Sinatra?- #had to look this one up. Sinatra is a domain specific language written in Ruby used for creating web applications.

4. What is MVC?-A pattern that dictates how we access information from a database. It stands for Model View Controller.  The model is what actually executes the commands to the database, the controller directs the responses to requests, and the views are accessed by the controller to render the html so that the user can see the information.

5. Why do we follow conventions when creating our actions/path names in our Sinatra routes? #Umm.. it's called using RESTful routes, but I think that's useful because it's easier to debug/follow the code? And because this guy wrote about it in his thesis? Maybe?

6. What types of variables are accessible in our view templates without explicitly passing them? Instance variables

7. Given the following block of code, how would I pass an instance variable `count` with a value of `1` to my `index.erb` template?

  ```ruby
  get '/horses' do
    #@count = Horse.all.count
    erb :index
  end
  ```

8. In the same code block, how would I pass a local variable `name` with a value of `Mr. Ed` to the view? #I actually have no idea.

9. What's the purpose of ERB? So you can use Ruby code inside HTML.

10. Why do I need a development AND test database? #Maybe because you want to test with a smaller dataset so it's faster and easier to debug? And also maybe so that you can manipulate the data in the test database without worrying about messing up important stuff?

11. What is CRUD and why is it important? Create, Read, Update, Destroy.  Those are the basic functionalities of an MVC (or kind of really anything--like what you can do to a webpage or to a database).

12. What does HTTP stand for? Hypertext Transfer Protocol

13. What are the two ways to interpolate Ruby in an ERB view template? What's the difference between these two ways? With or without an equal sign (.e.g <%= thing %> or <% thing %>).  The one with an equals sign renders the content of the ERB tags, and the one without evaluates the content of the ERB tags without rendering.

14. What's an ORM? Object Relational Mapper--it takes data and then converts that data into actual instances of objects that you can interact with using Ruby (like call methods on).

15. What's the most commonly used ORM in ruby (Sinatra & Rails)? Active Record

16. Let's say we have an application with restaurants. There are seven verb + path combinations necessary to provide full CRUD functionality for our restaurant application. List each of the seven combinations, and explain what each is for.
  -GET: /restaurants (display all restaurants)
  -GET: /restaurants/:id (display information for one restaurant)
  -GET: /restaurants/new  (see form to create restaurant)
  -GET: /restaurants/:id/edit (see form to update)
  -POST: /restaurants (create a task)
  -DELETE: /restaurants/:id (delete a task)

17. What's a migration? It's a set of instructions for how to create/update a database.

18. When you create a migration, does it automatically modify your database? No--you have to actually run the migration using rake db:migrate.

19. How does a model relate to a database? Models are the part of the MVC that actually interact with the database--to CRUD the information.

20. What is the difference between `#new` and `#create`? New instantiates an instance but doesn't save it, and create instantiates and does save it.
