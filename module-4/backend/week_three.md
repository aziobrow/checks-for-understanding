## Week Three - Module 4 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR.

1. At a high level, what is Node?
Node is a JavaScript runtime that allows JavaScript code to be run outside the browser.

2. What is Express? What is Express similar to in the Ruby world?
Express is a JavaScript framework, similar to Rails in Ruby (but less opinionated)

3. How do we setup a route when creating an API with Node and Express? Please provide a code snippet.
In app.js:
var dashboard = require('./routes/dashboard');
var app = express();
app.use('/', dashboard);

In /routes folder:
dashboard.js

In dashboard.js:
var express = require('express');
var router = express.Router();

router.get('/', function(req, res, next) {
  res.render('dashboard', { title: 'Quantified Self' });
});

module.exports = router;


4. What do we use Knex for? Knex is an sql query builder for node.js.  It has some of the functionality of ActiveRecord in Rails.  

5. How could you organize your code to follow the MVC design pattern in your Quantified Self project?
You could create a model folder that would contain the files/functions that access the database directly.  You'd then export those files to another folder called controllers that would have files handling the logic of taking in the request from the browser (e.g. parsing params) and making the call to the model functions.

6. How do you execute raw SQL in node?
I think there are probably multiple ways, but the way we looked at in class used the knex library--specifically, the knex.raw('RAW SQL HERE') syntax.

7. What are some advantages to having your front end and back end code live in separate applications? What are some disadvantages? They can be developed simultaneously, separation of concerns (essentially more SRP in design), more maintainability, gives you more modularity in the components.  Cons: feels like more work to test and deploy two separate components. Can be confusing since the two parts have to be structured exactly such that they can communicate with each other.

#### Review  

8. Describe DNS.  Domain Name Servers: an internet protocol that essentially takes user-friendly domain names (such as google.com) and translates those into computer-friendly IP addresses (DNS name resolution).

9. What does writing clean code mean to you? Following good maintainability practices, such as SRP, DRY, and follows principles of OOP (if that's appropriate for the language you're using). Variable names are easy to read, classes and methods are clear and SRP. Code has been tested for happy and sad paths.

10. If you were building an application that models hotels, what classes would you need? What classes would be responsible for what functionality? Hint: think about what tables you would need in the database, how those records would relate to each other, and good OOP.  I'm not overly well-versed in how hotels work, but I kind of picture it such that a company has many hotels, hotels have many rooms and reservations.  Guests and hotels would be many to many.  If we're talking staff, a staff member could belong to a hotel, but the relationship could also be many to many. Obviously, there could be a lot more here-like events, amenities, restaurants, cities, etc.  But I think that covers the basics of at least hotel structure. 
