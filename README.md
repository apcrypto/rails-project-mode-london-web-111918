# Rails Project Mode - Pet Sits R Us app created by Andy Purbrick and Serena Nakatani-Brown

## Project Requirements:

1. You should have least four models. You do not have to have all of these built out on day one. But by the end of the week, you should have at least four models.

2. Some methods in your models. There should be at least twenty methods total in your models. These are to be used to better extract data from your tables. Think Flatiron BnB Lab

3. No APIs until you get approval from an instructor.  The reason is because API's oftentimes leads you to learning the specific API really well, but not learning Rails that well.  Rails is a more transferable skill.  So stick with that.

4. Specs - there should be at least 10 specs in your project (five per person). 

5. An analytics page - The main learning goal of this is to get you to write some interesting activerecord queries.

6. No JavaScript. Stay focused on Rails for this project - we'll have plenty of time this semeseter to cover JS topics. 

## Project Task Guidelines
- come up with idea, model out domain. 
- add model tests, start building out basic features. Have some functionality built out by the end of the day. 
- Iterate on the features that you built yesterday. Go from a 'skateboard' version to a scooter or a bicycle. It doesnt' have to be perfect, but it should be working. 
- start styling/ cleaning up issues. 
- issue cleanup and final demos. 

## Project Scope and Ideation 

Not including the Christmas holiday period we had a total of 4 days to come up with a viable MVC web app and present a finished working version to all students at Flatiron London. 

After discussing various potential ideas we quickly settled on a pet sitting app that allows pet owners to book sitters online to cover periods where they're away or unable to care for their pets themselves. As per the project requirements we used an MVC framework and built the app using Rails with no JavaScript. We also avoided using an api as a data source specifically so we could focus on building our app and all the methods required to make it function.

Our app had four models with the following relationships:

1. Owners
  has_many :pets
  has_many :appointments, through: :pets
  has_many :sitters, through: :pets

2. Sitters
  has_many :appointments
  has_many :pets, through: :appointments
  has_many :owners, through: :appointments

3. Pets
  belongs_to :owner
  has_many :appointments
  has_many :sitters, through: :appointments

4. Appointments
  belongs_to :sitter
  belongs_to :pet
  
Functionality includes:

1. Ability to create and edit an owner profile with username and secure password
2. Ability to add and edit pet profiles
3. Ability to view sitters and make appointments with the sitters of your choice
4. Ability to delete pets and owner profiles

Various validations were implimented:

validates :username, :presence => true, :uniqueness => true, :length => { :in => 3..20 }
validates :email, :presence => true, :uniqueness => true
validates :password, :confirmation => true
validates_length_of :password, :in => 6..20, :on => :create

## Project Development and Division of Tasks
Day 1
- Project was specced out and file structure was created 
- Seed data created and migrated to app

Day 2
- Started build for models, controllers and views
- By end of the day we had a fully functioning but ugly and buggy app

Day 3
- Trouble-shooting bugs
- Cleaned up pages for example registration forms and worked on user journey/flow
- Styling pages with Bootstrap and CSS

Day 4
- Final clean-up of styles so that everything displayed properly 

In terms of division of work we sat together when required and divided up tasks and worked seperately for some periods. Generally speaking we kept in close contact and were extremely careful when committting and changes to Github.

## Challenges
We were both new to Github and it was often challenging to keep version control in check but we were very cautious and no mistakes were made.

We were both totally new to styling a Rails app using Bootstrap so we ended up spending quite a bit of time getting the app looking good. Thankfully, we had built out the back-end in good time so we could spend time refining towards the end of the project.

## Learnings
We decided not to create an app that used a public api, in hidsight this was a really sound decision as it stopped us getting bogged down in non-Rails activities and gave us enough time to produce a relatively high standard piece of work.

It probably would have paid to read more about Bootstrap prior to implimenting it on the project. We spent quite a bit of time getting styles working correctly but we got there eventually and we learned some vital lessons around.


