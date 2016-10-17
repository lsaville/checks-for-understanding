## Week Two - Module 2 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON - YOU are a web developer!!!). 

Note: When you're done, submit a PR. 

1. At a high level, what is ActiveRecord? What does it do/allow you to do?<br>

ActiveRecord is a piece of rails that can be used independently. It does Object Relational Mapping which interacts with a database through models (which are our objects) that go between the database and the views. It provides a ton of built in functionality to make our lives easier, based on the idea that convention should be triumphed over configuration. 

2. What is a migration?<br>

A migration is a file/set of instructions for building the database. In the migration files we say which tables we want with what columns and additionally we can change something that has already been created i.e. rename columns, add columns, delete, etc.

3. How does a table relate to a model?<br>

Due to the rails "magic", a model looks at the table and assumes that we would like the model object to have attributes that correspond to all the columns in a given table. A table is the database and the model is built off of it. The model seems to be our way of interacting with the database also. We can create relationships between tables and thus models.

4. What kind of methods are `belongs_to`, and `has_many`? (i.e. class or instance) Give an example.<br>

I would say that these relational methods are instance methods. An article belongs to its author, and if we had the whole thing set up we could assign a particular author to a variable and then call articles on it i.e. `author = Author.first` & `author.articles` and it should bring up all the articles belonging to that particular author (compared with calling Article.all). 

5. What do they allow you to do?<br>

I'm not sure its appropriate to invoke the word "scope", but in a way they allow you to scope down into collections of things based on their relationships. I've been thinking about it like searching from the perspective of the end point of one of the relationships. 

6. What's the difference between agile workflow and waterfall method?<br>

Agile takes as its philosophy that a client never knows what they want until they can see it and that a project should be approached doing a little bit of everything(in terms of design, planning, build-out, testing) developing iteratively. Waterfall is the approach that some enigneers sit down and try to think of how a thing should be at the end down to the last detail. They design it and that it, thats the final design. They then pass it off to another team and the progression goes in strict order.  

7. What is the difference between `#new` and `#create`?<br>

`#new` gives us a blank object with all the attributes being nil. We can use it to check what attributes it has or apparently we can use it as a placeholder for some crazy rails thing called reflection. If we assign the new object to a variable we can fill its attributes and `.save` to make those changes in the database. `#create` does all that at once, makes the object and saves it. 

8. At a basic level, what does cURL allow you to do?

cURL is a command line utitlity that allow you to go to a resource online, grab it and bring it back.

9. In a database that's holding students and teachers, what will be the relationship between students and teachers? Draw the schema diagram.

At its simplest a teacher will have many students and a student belongs to a teacher. In reality perhaps it would be the case of many to many as students have multiple teachers. 

In the simple case the student table would have a foreign key that corresponds to a teacher_id. In a slightly more complex case the teachers and students would be tied through a joins table that would contain id, teacher_id, and student_id. More complex still would be to have the third table have its own attributes, perhaps we could call it curriculum. A teacher would have many students through curriculum and a student would have many teachers through curriculum (curriculum in the sense of program or track). A curriculum would have many students and would have many teachers. 

10. Define foreign key, primary key, and schema.<br>

A foreign key is something_id and will be a part of the table that has the belongs_to. A primary key is a unique identifier(which apparently can be a compound multi-column key if the example calls for it). A schema is a description of how the database is set-up. 

11. Describe the relationship between a foreign key on one table and a primary key on another table.<br>

The foreign key in the one table is the primary key from the other. The table with the foreign key will also have it's primary key.

12. What are the parts of an HTTP response?<br>

I think this is the bit about the three parted thing that rack is based off of. There is the status code and the body(which might be plain ol' html). I'm unable to remember the third part currently.

13. `Rack::Test` allows us to test our controllers in isolation. What are some of the methods it gives us to simulate the request/response cycle?<br>

I'm not sure I got to any of that, but in theory at every point of contact with the "outside" world you could just give it a stock response mock/stub style, to make sure it's behaving as you'd want it to in a given circumstance.


14. Describe some techniques to make our Sinatra views more DRY. Give an example of when you would use these techniques.<br>

One technique we can use is having the layout page, which factors the elements that each individual page would have in common with all the others out into one thing that does the same thing for everypage. Now that I've seen it in action, we could also have partials, which are similar in that they are reducing repition by pulling the common bit out to be used by many pages instead of having the same thing in the many pages. We used this in the blogger tutorial to not repeat a form.


### Optional Questions

1. Name your five favorite ActiveRecord methods (i.e. methods your models inherit from ActiveRecord) and describe what they do.<br>

`.all` grabs all the things you want. `.find` which takes a straight parameter of id and will fetch the specific thing you want. `.find_by` which will find the thing you want by an attribute besides id. `.new` which saves me from thinking too hard about which attributes belong to which object, like a cheat sheet for properly creating the object. `.create` which does the creation in one fell swoop after I checked the new object. `.find_or_create_by` which checks to see if you've got one, if you don't it'll make you one.  

2. Name your three favorite ActiveRecord rake tasks and describe what they do.<br>

`rake db:test:prepare` which I think will take all the stuff you implemented in your development environment and implement it in the test environment so that you can be on the same page as yourself when testing(if you don't do this bad things happen). `rake routes` which goes in a grabs all the various routes you've defined and tells you the prefix and what action goes where. `rake db:migrate` which takes the stuff you put in the migration file and attempts to make it database reality. 

3. What's the difference between agile workflow and waterfall method?<br>

Duplicate question see #6 above

4. What can you expect from a group as you begin working together? As you continue working together?<br>

I feel that at Turing I can expect that everyone cares very much about the outcome of the project. On a continual basis I think a group would get better in the areas in which they struggle, perhaps adhering the the group development scheme we talked about in class (the forming, storming, performing, adjourning deal). 

5. What two columns does `t.timestamps null: false` create in our database?<br>

It creates a created_at and an updated_at column which are automatically 'timestamped'.

6. What cURL flag can you use to send a `POST` request?<br>

No idea. -P?

7. What case does JSON (and JavaScript) use for multi-word variables?<br>

Over in javascript land they use camelcase... I think more specifically they use a camelcase that starts with lower case. I know the ruby crowd talks about using CamelCase in ruby classes and such but js uses camelCase I'm pretty sure.

8. What case does Ruby use for multi-word variables?<br>

Ruby uses snake_case.

9. In a database that's holding schools and teachers, what will be the relationship between schools and teachers?<br>

Duplicate question, see #9 above.

10. In the same database, what will you need to do to create this relationship (draw a schema diagram)?<br>

#9 above.

11. Give an example of when you might want to store information besides ids on a join table.<br>

There might be a case where a third party in the relationship is important... a join table seems slightly artificial. To bring the example closer to home, turing has many students. A student has many teachers(not THAT many but...). A teacher has many students. A student has many teachers through the program they're in (i.e. FEE BEE). A teacher has many students through that same program. The program itself is quite different, has different curriculum, exists in a different location, has different teachers. I'm not sure how modules would come in but I'm sure you could do something there. Basically you might want to store information there because it would accurately represent something in reality.

12. Describe and diagram the relationship between patients and doctors.
13. Describe and diagram the relationship between museums and original_paintings.
14. What are some examples of acceptable values for the parts of an HTTP response?
15. What types of output do we want to test when we test our controllers?
16. What could you see in your code that would make you think you might want to create a partial?
17. Why might you use a helper method?
