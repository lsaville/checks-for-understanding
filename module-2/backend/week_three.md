## Week Three Recap

### Instructions
Fork this repository. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Questions

1. What are the 3 main features in an ERD?
<br>
I don't think I ever heard the term ERD before.... but it seems to be the thing where we draw out the schema. The main features are a visual representations of the various tables in the database, each table having its perspective columns, and that they have a line drawn between the id of a has many table to the the corresponding foreign key of the belongs_to table.

2. Create an ERD for the following database: Restaurants, Customers, Items, Ingredients, Beverages, Orders, Vendors.<br>

In my notebook.  

3. What is the entry at the command line to create a new rails app?<br>

rails new project-name

4. What do Models generally inherit from in rails?<br>

rails models inherit from ActiveRecord::Base and this gives them all the shiny methods of activerecord.


5. What do Controllers generally inherit from in a rails project?<br>

Controllers inherit from ApplicationController

6. How would I create a route if I wanted to see a specific horse in my routes fitle assuming I'm sticking to standard conventions and that I didn't want other CRUD functionality?<br>

In your routes you could say resources :horses, only: :show

7. What rake task is useful when looking at routes, and what information does it give you?<br>

rake routes gives you a list of all the routes set-up prefixes so you can use the route helper methods.
  
8. What is an example of a route helper? When would you use them?<br>

Most commonly I've used the path helper that goes something like company_job_path(company, job) and it spits out the url for the particular job at a particular company according to the parameters it is passed. This is super handy when creating links.

9. What's the difference between what `_url` and `_path` return when combined with a routes prefix?<br>

I'm not sure, I've not used _url.

10. What are strong params and why are the necessary?<br>

Strong parameters are a safety feature of rails the prevents mass assignment without the specification of which parts of the params you want to permit and protects against sequel injection attacks. It prevents someone from submitting sneaking things in through the params.

11. What role does `form_for` play in helping us create our forms?<br>

form_for is a helper method that creates a form for a specific object, making sure all the ducks are in order for that given object. This allows us to use the syntax rails provides and simplifies the whole process in making a form. 

12. How does `form_for` know where to submit the user's input?<br>

Presumably form_for knows where to submit based on the object in it parameters, that maps back to the routes and database.

13. Create a form using a `form_for` helper to create a new `Horse`.<br>
``` erb
<%= form_for @horse do |f| %>
  <%= f.label :name %>
  <%= f.text_field :name %>
  
  <%= f.label :breed %>
  <%= f.text_field :breed %>
  
  <%= f.submit %>
<% end %>
```
14. Why do we want to validate our models?<br>

Validating our models ensures us that we will be protecting the integrity of our database by checking if the validations are doing their jobs. 
