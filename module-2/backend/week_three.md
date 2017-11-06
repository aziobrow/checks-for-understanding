## Week Three Recap

### Instructions
Fork this repository. Be sure to pull the latest changes to your local repo. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Questions

1. What is the entry at the command line to create a new rails app?
  rails new app_name.  You can also add -T to get rid of the test folder (so you can replace with rspec later) and --database=postgresql to change the database from default SQLite to Postgresql.

2. What do Models generally inherit from in rails?
  ApplicationRecord

3. What do Controllers generally inherit from in a rails project?
  ApplicationController

4. How would I create a route if I wanted to see a specific horse in my routes fitle assuming I'm sticking to standard conventions and that I didn't want other CRUD functionality?
  resources :horses, only: [:show]

5. What rake task is useful when looking at routes, and what information does it give you?
  rake routes--it gives you a little table with all of the available prefixes, verbs, uri patterns, and controller actions, as defined by your config/routes file.

6. What is an example of a route helper? When would you use them?
  muffin_path(@muffin)-  The router would then generate the path /muffins/:id for you. You would use them when you're creating links, buttons (EXCEPT BUTTONS DEFAULT TO POST METHODS, I LEARNED TOO LATE, GRRR) within a view, or redirecting within a controller action.

7. What's the difference between what `_url` and `_path` return when combined with a routes prefix?
  Pretty sure this is the thing where `_path` is a relative path from the root of the site, and is almost always preferred.  Otherwise, you can use the `_url` which is an absolute path that includes protocol and server name, which we mentioned might be useful with emails.

8. What are strong params and why are the necessary?
  Strong params are the result of a private controller method that takes the broader params and says what parts it's okay to use. It's a security thing, I think. Is it right that it wouldn't work if you tried to use just params instead of the strong params?

9. What role does `form_for` play in helping us create our forms?
  It's a form helper that allows the developer to create a form with sort of minimal effort. You just have to define the labels, input type, and attribute for each part of the form, and add the submit button.

10. How does `form_for` know where to submit the user's input?
  Is this a question about going to a new form or an edit form? That's the .persisted? thing where it knows whether the object is new or has data that has been persisted. Or is this a question about how it knows what column within the database to store the information? In that case, it's when you define the form specifics inside the form_for helper. E.g., f.text_field :name stores the information to the name column for that view's model.

11. Create a form using a `form_for` helper to create a new `Horse`.
  <%= form_for @horse do |f|  %>
  <%= f.label :name %>
  <%= f.text_field :name %>

  <%= f.label :breed %>
  <%= f.text_field :breed %>

  <%= f.submit %>
  <% end %>

12. Why do we want to validate our models?
  We want to make sure that we get the necessary information that we need when a new object is created. For example, we want to make sure that new users are created with a password, or that two users don't have the same password. We can check for presence and uniqueness of those attributes upon attempted creation. 
