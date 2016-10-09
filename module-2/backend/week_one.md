## Week One - Module 2 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON!). 

Note: When you're done, submit a PR. 

1. List the five common HTTP verbs and what the purpose is of each verb. <br>

GET - hits up the server for a resource and displays that resource to the user if it's found.
POST - sends some stuff to the server where it changes something in accordance.
PATCH - updates a thing (can also be post).
DELETE- deletes something in the database... i.e a robot

2. What is Sinatra?<br>

Sinatra is like a mini-rails where you can create CRUD functionality on the backend. You hook it up with a database and can optionally mimic MVC design if you set it up that way. It has routes that correspond to the http-verbs and lets you interact with the database from the browser through the controller.

4. What is MVC?<br>

MVC is a design principle set using the paradigm of Model, View, Controller. The controller routes everything, checks the model and then serves up the view by grabbing the info from the model and erbing it into some html which is shown.

5. Why do we follow conventions when creating our actions/path names in our Sinatra routes?<br>

We follow the conventions so that our code is approachable by anyone in the community. These are conventions that have evolved overtime and allow us to know that generally a given path name is related to a specific thing. I remember also (not exactly sure when/why we'd need to) that it would enable you to navigate through a page without using buttons/links.

6. What types of variables are accessible in our view templates without explicitly passing them?<br>

Instance variables are available in the view templates. That being said, the instance variables need to be defined within the route connected to the view (as opposed to ivars being available throughout a given class). Optionally we can pass local variables using the locals hash.

7. Given the following block of code, how would I pass an instance variable `count` with a value of `1` to my `index.erb` template?
  
```ruby
get '/horses' do
  @count = 1
  erb :index
end
```

8. In the same code block, how would I pass a local variable `name` with a value of `Mr. Ed`?
  
```ruby
get '/horses' do
  name = "Mr. Ed"
  erb :index, locals: {name: name}
end
```
9. What's the purpose of ERB?<br>

Erb allows us to inject the results of our ruby code into some other type of code (i.e. html). I think of it like interpolation but in the context of a file instead of a string. This allows us to pull data from our model and wrap it into html which is appropriate for presentation in the browser.

10. Why do I need a development AND test database?<br>

You need both databases because you don't want your tests to be manipulating the actual dataset you're working with. I think I heard something like dirtying/muddling the original database. Additionally in our testing environment we're "cleaning" our database between each "it" block.

11. What's responsive design?<br>

Responsive design refers to web pages that can be displayed beautifully regardless of the device the viewer is using.

12. What is CRUD and why is it important?<br>

CRUD is a design paradigm with databases for persistent storage. These are all the functions you need to have a functional data storage system. Create, Read, Update, and Delete.

13. What does HTTP stand for? <br>

HyperText Transfer Protocol

14. What are the two ways to interpolate Ruby in an ERB view template? What's the difference between these two ways?<br>

`<%= %>` and `<% %>`. The first displays the evaluation of the ruby code within while the second evaluates but doesn't display.

15. What's an ORM?<br>

An ORM is an object relational model. This describes the situation where an object is a go between a database and the view in MVC.

16. What's the most commonly used ORM?<br>

ActiveRecord 

17. Let's say we have an application with restaurants. There are seven verb + path combinations necessary to provide full CRUD functionality for our restaurant application. List each of the seven combinations, and explain what each is for. <br>

get '/restaurants' to show all restaurants

get '/restaurants/:id' to show an individual restaurant

get '/restaurants/new' to show the form for adding a new restaurant

post '/restaurants/new' to actually add the stuff from the form, touching the database

get '/restaurants/:id/edit' to show the form for editing a restuarant

post '/restaurants/:id' to actually add the from from the form, updating the info in the database

delete '/restaurants/:id' to delete a restaurant

18. What's a migration? <br>

A migration sets up a migration file that you can put things into to make a new table. It is how we interact with the database.

19. When you create a migration, does it automatically modify your database?<br>

Just creating the migration doesn't modify the database, but if you migrate that migration it will.

20. How does a model relate to a database?><br>

They are directly intwined... that is to say that the model is the object that goes between the database and the view and is where the functionality for that object lives (both from ActiveRecord convenience methods and from custom methods that we write in the model.


