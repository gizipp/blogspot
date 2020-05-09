---
layout: post
title: "20 Days of Rails!"
description: "Jurnal catatan belajar Ruby on Rails selama sebulan atau 20 hari jam kerja. Halah."
category: io
tags: [rails]
---

Di training Ruby (on Rails) oleh mas Gilang kepada Gilang satunya. Selama 20 hari yang dipelajari ini...

* Table of Contents
{:toc}

## Hari ke-1

*8/9/2014 (1)*

- Introduction of Ruby On Rails.
- Learning ruby, git, gem and installation+setup.
- Installing Ruby On Rails+libs
- Creating simple CRUD blog apps+devise

Task: Creating simple function and class, and extend. (Completed)

## Hari ke-2

*9/9/2014 (2)*

- Self Learning : Ruby On Rails Install dari awal, scaffold
- Git Basic+setup
- Active Record Associations

Tommorow Task
- Task : CRUD blog -> comments

## Hari ke-3

*10/9/2014 (3)*

- [Task] Simple Blog Crud update comment -> dropdown. Active Record Assosiation.
- Learning Active Record Query Interface
- Create + setup Repo in bitbucket
- Setup new app (Rails+mySQL)
- [Task] Project Management Software
  -> Creating users with gem devise

Tommorow Task
- [Task] Project Management Software -> Creating users with gem devise

## Hari ke-4

*11/9/2014 (4)*

Project Management Software

- User validation for role, username
- Default User Role after register is member
- Create works model

Tomorrow Task : Project Management Software

- User can create Project
- User who create the project can invite contributors
- Only user who create the project can delete the project

## Hari ke-5

*12/9/2014 (5)*

Project Management Software

- CanCanCan authorization
- User can delete and edit Project
- Relation user, work, contributor

Tommorow Task : Project Management Software

- Contributor invitation
- Pagination

## Kesimpulan Minggu ke-1

Nanti ya

## Hari ke-6

*15/9/2014 (6)*

Project Management Software



- Todo list module
- Task list module
- Send mail when task assigned and add asynchronous sidekiq on mail job

Tommorow Task

- Fixing bugs send mail
- Create polymorphic association on comment and task

## Hari ke-7

*16/9/2014 (7)*

Project Management Software

- Fixing send mail when user sign up and user assigned new task
- Create attachment polymorphic association on comment and task
- User can attach file on task
- User can attach file on task comment
- Ignore shared files and folders  .gitignore

## Hari ke-8

*17/9/2014 (8)*

- Self Learning : Install RefineryCMS and learn the code
- Self Learning : https://tryruby.org/ (Completed)
- Reading “RAILS ANTIPATTERNS  Best Practice Ruby on Rails TM Refactoring” (BAB 1. Model)

Project Management Software

- Show all task only for admin, member only can view their only task
- Show user list and roles of user
- Role ability + authentication changes
- Work on views add new project, task, todo list, etc

## Hari ke-9

*18/9/2014 (9)*

Project Management Software

- Project show the contributors and to do list
- Contributors and users management
- Changes on contributors etc
- Appearance tweak

## Hari ke-10

*19/9/2014 (10)*

Break and pray.

Ice Cream Cup.

Project Management Software

- Changes route task, todo list nested into route work
- Contributor feature changes and validation
- Add contributor
- Add to do list

## Kesimpulan Minggu ke-2

Nanti ya...

## Hari ke-11

*22/9/2014 (11)*

Lunch break and pray.

Algorithm test - Logic training : ATM simulation

Training Text Editor: Sublime Text.

Project Management Software

- Nested routes changes on task/comment/attachment
- Todo list modul changes to match the nested routes
- Modify show task, comment and add comment
- Misc

## Hari ke-12

*23/9/2014 (12)*

Breack and lunch.

- Setup workspace → Text editor Sublime Text + emmet and learn shortcut
- Setup 'getting started Heroku apps' (ruby)

Project Management Software



- Fixing user can't assign himself as contributor
- Welcome email testing and changes
- User mailer changes etc
- Update gemfile for production : pg, rails_12factor
- Create production site pmspms.herokuapp.com
  Status = On issue, can't done 'heroku run rake db:migrate' perfectly (only 5 from 10 tables created)

## Hari ke-13

*24/9/2014 (13)*

Breack and lunch.

- pgsql setup on local

Project Management Software

- Fixing production site pmspms.herokuapp.com issue -> db:reset and remigrating
- Change task listing into table view on todo list view.
- Show info due date, completed status on todo list view.
- Add validation on due date. User can't set due date on the past.
- Change due date coloumn into X days left
- Some changes on edit and add new task
- Add new task fixing -> user can assign contributor of the project only
- Show the contribution number of user on users view
- Show the number of on progress/completed task on works view

## Hari ke-14

*25/9/2014 (14)*

Break, pray and lunch.

- Reading "Beginning Rails 4, 3rd Edition" Chapter 10: Sending and Receiving E-Mail
- Learning again about Rails 4 directory structure, route etc
- Creating simple apps/project using OmniAuth 'sign in via Twitter'

Project Management Software

- Gemfile update etc
- Investigate the action mailer (nofify when user assigned new task)
- Creating user, work, todo list, task seeds using faker gem
- Show user changes

## Hari ke-15

*26/9/2014 (15)*

Break, pray and lunch.

- Reading "Git- Version Control for Everyone" (ch.1 - 6)
- Reading "Algorithms in a Nutshell" (ch.1 Algorithm Matter!)
- Learn regex and try https://regexone.com/

Project Management Software

- Recreate pmspms.herokuapp.com due to push conflict on /tmp folder
- Run db:seeds on heroku and add dummy content
- Fixing on add new task error since the changes of the route (22/9/2014)
- Work on action mailer -> welcome email and new task assigned
- Install redis server for sidekiq and add sending emails asynchronously/delay

Tomorrow Task

- Reset password https://pmspms.herokuapp.com/users/password/new doesn't work
- Work on comment attachment and task attachment

## Kesimpulan Minggu ke-3

Nanti ya...

## Hari ke-16

*29/9/2014 (16)*

Break and lunch.

- Setup Zoo
  Status : On issue, can't found 'rdoc/task'

Project Management Software

- Attachable and attachment changes
- Fixing on task attachment after the changes of the routes
- Refactoring works model+controller (pending)

## Hari ke-17

*30/9/2014 (17)*

Breack and lunch.

- Reading "The RSpec Book" Chapter RSpec
- Reading “RAILS ANTIPATTERNS  Best Practice Ruby on Rails TM Refactoring” (Fat Models)

Zoo Property

- Setup Zoo. Status : Completed
- Learning how Zoo system work, the code, lib, misc, etc

Robot Coding Test

- Create simple Robot application in Ruby
- Create unit test with Rspec on Robot

Project Management Software

- Refactoring works model+controller (pending)

## Hari ke-18

*1/10/2014 (18)*

Break and lunch.

- Learning git branch management, merging etc
- Re-reading "The RSpec Book" Chapter RSpec
- Learning ruby operators https://www.tutorialspoint.com/ruby/ruby_operators.htm

Robot Coding Test

- Many changes on code and test cases https://github.com/gizipp/robot-coding-test/tree/master

Zoo Property

- Add field on Zoo (Client section)
- Update field default value misc

## Hari ke-19

*2/10/2014 (19)*

Break and lunch.

- Learning ruby operators https://www.tutorialspoint.com/ruby/ruby_operators.htm
- Learning the functional of Zoo system
- Reading Rails Guides 2.3.11 https://guides.rubyonrails.org/v2.3.11/

Zoo Property

- Fixing rspec problem cause can't run rake jobs:work etc
- Add new menu on ACCOUNTS tab and new field :honor

## Hari ke-20

*3/10/2014 (20)*

Break and lunch.

- Reading Rails Guides 2.3.11 https://guides.rubyonrails.org/v2.3.11/
- Learning the functional of Zoo system
- Ruby Example Code https://sandbox.mc.edu/~bennet/ruby/code/index.html (basic + Control Structures)

Zoo Property

- Install and config rails-dev-boost gem for faster developments
- Add new office modification + map

## Kesimpulan Minggu ke-4

Nanti ya...
