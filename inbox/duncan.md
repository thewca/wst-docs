# Random notes: 

- example of good code commenting: https://github.com/ablakey/gameboy/blob/master/src/guest/systems/ppu.rs

- maintenance load not technical debt: https://stackoverflow.blog/2023/02/27/stop-saying-technical-debt/?cb=1

- creating warnings on results validation is done by WST - WRT has no special tools to do this.

- registration opening query:
  select id, registration_open, competitor_limit from Competitions
  where registration_open between '2023-02-26' and '2023-03-01'
  order by registration_open

- codebase style suggestions
  - avoid implicits wherever possible - implicits are VERY confusing for new contributors, and being explicit makes it easier for people who aren't you to follow what your code is doing
    - use explicit returns in fucntions
    - use brackets() for function calls - even when there are no arguments


# Ruby cheatsheet

## Commands
Generate a model: `bin/rails generate model <model_name> <property_name:property_type>`
  - <model_name> is singular, and capitalised (eg, "User")
  - Property types: `string`, `text`
  - After property names, you can use <other_model_name:references>, eg `user:references`
  - This creates the following:
    - db/migrate/<migration script>
    - app/models/<model_name>.rb 
    - test/models/<model_name>\_test.rb  	<= Testing harness for the comment model
    - test/fixtures/<model_name>.yml  <= Samples of the model for use in testing
  - if the model you created references another model, update the model file of the associated model with a `has_many` clause

Generate a controller: `bin/rails generate controller Comments`
  - This creates the following:
    - app/controllers/<controller_name>\_controller.rb <= controller file
    - app/views/comments <= stores views for the controller
      - Note that a controller is a file, but its views are in a folder. One controller can have many views (eg, to execute different CRUD operations on a model)
    - test/controllers/<controller_name>\_controller_test.rb <= tests for controller
    - apps/helpers/<controller_name>\_helper.rb <= helper file for the view (not really sure what this does yet)

## Route definitions

# Beginner's guide to contributing

## Contributing workflow

- write PR
- run pre-commit hooks (how to do this?)
- run tests (how to do this?)

## Learning the stack

1. Learn Ruby
> Odin project Ruby section is great, a few hours if you are already experienced in another language



2. Learn Rails
> Diagram of overall architecture: https://se-education.org/learningresources/contents/ruby/mvc.jpeg
> This rails guide is phenomenal at showing you the conventions of Rails, and giving you a taste of its power: https://guides.rubyonrails.org/getting_started.html
> (This stackoverflow summary)[https://stackoverflow.com/questions/5205002/summary-of-ruby-on-rails-fundamental-concepts]
> The Odin Project has a great course
> Video lesson
> Our own introductions

## Seeing through rails magic
https://www.youtube.com/watch?v=rssgWqJq-14

## Why rails?

Great discussion on reddit:
https://www.reddit.com/r/rails/comments/aho9g0/hoping_to_view_rails_magic_through_a_different/
https://medium.com/swlh/the-ups-and-downs-of-rails-magic-5a88c7f68064
https://rubyonrails.org/doctrine


Once you know rails, your fluency in the code goes up MASSIVELY. But, it is a barrier to contributing. 

2. Setting up a local copy of the website

3. Running the local copy of the website
> bringing in a database
> updating your branch

# Wiki ideas: 

- support requests
  - changing email for delegate
    - WRT handles this


- general noob notes
  - code in the docker instance changes when you switch git branches
- rails for noobs
  - popups come from optimiser called bullet, You can shut it of by creating a file called `.env.development.local` under `WcaOnRails` with the following contents: `DISABLE_BULLET=true`
- project management section
  ? where to create this? it's own file? inside wst-internal? 
- using the dev server
  - log in to anyone's account by using WCA ID as email, and "wca" as password 
  - DATABASE
    - you don't start off with any data from the database. This command downloads the latest dev db export: 
      - `bin/rake db:load:development`
    - this command takes a long time (70 minutes)
- staging
  - database has to be manually updated
- statistics 
  - updates twice per week

- common email queries

- Importing Registration Data
  - Import CSV format is the same as the format of the CSV you get when exporting registration data fro a competition
  - Refer to the (Example CSV)[https://drive.google.com/file/d/1yWInQOOOe23satlm7igEAeaQOCYK3Nii/view?usp=sharing]
  - TODO: make a list of field names and input requirements

# TODO

[ ] Import everything that I've pinned in wst-project-management into the project management section
