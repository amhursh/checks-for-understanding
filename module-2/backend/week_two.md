## Week Two - Module 2 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON - YOU are a web developer!!!).

Note: When you're done, submit a PR.

1. At a high level, what is ActiveRecord? What does it do/allow you to do?

  ActiveRecord allows us to map objects to corresponding rows in database tables. It creates an ORM that allows us to use an object-oriented language (ruby) to store, use, and manipulate table data.

2. Assume you have the following model:

```ruby
class Team << ActiveRecord::Base
end
```

What are some methods you can call on `Team`? If these methods aren't defined in the class, how do you have access to them?

  You can call any methods defined within the Team class as well as methods such as new, save, create, destroy, etc. You can call those methods because they are inherited from ActiveRecord.

3. Assume that in your database, a team has the following attributes: "id", "name", owner_id". How would you find the name of a team with an id of 4? Assuming your class only included the code from question 2, how could you find the owner of the same team?

  Find team with the id of 4:

  ```ruby
  Team.find(4)
  ```

  Find owner of team with the id of 4 (assuming owner class exists and no owner relationship added to Team class):

  ```ruby
  Owner.find(Team.find(4).owner_id)
  ```

4. Assume that you added a line to your `Team` class as follows:

```ruby
class Team << ActiveRecord::Base
  belongs_to :owner
end
```

Now how would you find the owner of the team with an id of 4?

```ruby
Team.find(4).owner
```

5. In a database that's holding students and teachers, what will be the relationship between students and teachers? Draw the schema diagram.

  Here is an example:

  Teacher has_many students
  Student belongs_to teacher

  note: this would be a one to many relationship, but many to many is also reasonable here (depends on scope, i.e. class, school, etc.)

  Student
  id
  name
  gpa
  etc.
  teacher_id

  Teacher
  id
  name
  etc.

6. Define foreign key, primary key, and schema.

  Foreign Key - a column within a table that links to the primary key of another table and thus acts as a reference that connects the two tables
  Primary Key - a column that uniquely identifies each row within a table
  Schema - a 'map' of database tables and the relationships between those tables

7. Describe the relationship between a foreign key on one table and a primary key on another table.

  The foreign key on one table will correspond to a primary key on another table, thus linking the two datasets together.

8. What are the parts of an HTTP response?

  (had to look this one up, fyi)

  * Status-line - This includes the HTTP status code that defines the state of the transaction
  * Headers - information that defines the parameters of the http transaction (date, content-length, range, etc.)
  * Empty line or line-break
  * Message-Body (html, i think)

### Optional Questions

1. Name your five favorite ActiveRecord methods (i.e. methods your models inherit from ActiveRecord) and describe what they do.

  I like the following:

  * pluck - really fast way to get records columns that i want without iterating.
  * where - a really versatile way to select records that meet conditions (i especially like using this on arrays - magic!)
  * order - allows me to order selections by a specific attribute
  * group - allows me to take a selection of records and group them by some attribute
  * exists? - for troubleshooting and in actual practice, i just like to know if something is there. It's comforting.

2. Name your three favorite ActiveRecord rake tasks and describe what they do.

  I'm not sure if 'favorite' is a word i would use to describe rake tasks, but here is what i have found myself using a lot:

  * rake db:test:prepare - anytime i have phantom test-fails - i guess this checks migrations and loads the test schema
  * rake db:reset - runs db:drop and db:setup (db:schema:load and db:seed) in one go

3. What two columns does `t.timestamps null: false` create in our database?

  These add created_at and updated at columns to the table. They cannot be null.

4. In a database that's holding schools and teachers, what will be the relationship between schools and teachers?

  Probably a one to many relationship:

  Teacher belongs_to schools and School has_many teachers

5. In the same database, what will you need to do to create this relationship (draw a schema diagram)?

  Teachers table will need a foreign key, school_id, to indicate which school they belong to

6. Give an example of when you might want to store information besides ids on a join table.

  I think invoice-items (from black thursday) would be a good example. They contain information beyond invoice_id and item_id (like unit_price and quantity)

7. Describe and diagram the relationship between patients and doctors.

  Many to many relationship:

  Patient has_many doctors through doctors_patients
  Patient has_many Doctors_Patients
  Doctor has_many patients through doctors_patients
  Doctor has_many Doctors_Patients
  Doctors_Patients belongs_to Doctor
  Doctors_Patients belongs_to Patient

  Tables:

  Doctor
  id
  name
  dept.
  etc.

  Patient
  id
  name
  d.o.b.
  etc.

  Doctors_Patients
  id
  doctor_id
  patient_id

8. Describe and diagram the relationship between museums and original_paintings.

  One to many relationship:

  Original_Painting belongs_to Museum
  Museum has_many Original_Paintings

  Tables:

  Original_Paintings
  id
  artist (or artist_id, probably)
  year (or year_id)
  title
  etc.
  museum_id

  Museums
  id
  location
  name
  etc.

9. What could you see in your code that would make you think you might want to create a partial?

  Repetition of code in forms. Do i need to use it more than once?
