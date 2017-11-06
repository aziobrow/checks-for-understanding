1. How do we make flash messages display on a page?
You have to enable flash in your application layout.
<% flash.each do |type, message| %>
  <%= render 'flash_message', type: type, message: message %>
<% end %>

2. Where is cart information/temporary information usually stored?
In a session

3. What might be some reasons not to store cart in our database? Are there any reasons why we would want to persist that information?
A cart doesn't really mean anything until it becomes an order, and you don't want to be creating/updating/deleting rows in a database table every time a user adds or removes something from their cart.

4. What is the purpose of the asset pipeline?
The asset pipeline (I think) preps your front end stuff for you before production. So it minifies, concatenates, and pre-processes your assets for you. Minifying is basically cleaning up code (removing comments, removing unused code, etc.). Concatenating puts multiple assets into one file.

5. Why do we precompile our assets? Precompiling takes languages that need compiling (like CoffeeScript and Sass) and turns them into CSS and Javascript so that the browser can read them.

6. What do each of the following tags do?

```ruby
<%= stylesheet_link_tag "application" %>
I think it links to the file path where that page should look for css styling resources and appends a .css to it.


<%= javascript_include_tag "application" %>
I think it links to where that page should look for javascript styling resources and appends a .js to it.


<%= image_tag "rails.png" %>
```
Links to path where image is stored within assets folder.


7. What are some of the elements of a great read me? What are some of the benefits of taking the time to update a readme for our project?  
How to get/implement, defining the purpose, what features your app has, how it can be used in practice (e.g. code examples).  People actually use your stuff! If people can't figure out how to use it, it doesn't matter how great it is.

8. What are the top four accessibility issues that we as developers should be aware of?
Visual, Mobility, Cognition, Hearing

9. `before_save` is an example of a what? Where in our Rails application would we find a `before_save`?
Callback.  To generate a slug to be used in a file path.

10. Given the following object, how would we create a scope for all users who are active?

```ruby
User.create(name: "Happy", active: true)
```
 scope :draft, -> { where(active: 'true') }


11. What is the difference between a scope and a class method?
There isn't one? ActiveRecord converts a scope into a class method (behind the scenes, obviously, because Rails magic). But you can add conditions to scopes, and scopes will always return relations, whereas class methods don't always. You can also extend scopes by adding methods inside of them.  Did we talk about this in class?? This all seems very unfamiliar to me. Fortunately, the Google always saves the day. 
