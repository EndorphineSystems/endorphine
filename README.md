# Endorphine App Core

> Programming is hard. Admit it. Building a program with Endorphine will still
> hard and requires effort, but you will be happier building program
> in Endorphine.

## Concept

Endorphine App consists of three things:

- Module
- Flow
- Node

Those Endorphine components suggest their
directory structure. For example, following
is directory structure of the sample app.

    /
    /app.yml
    /module
    /module/user.yml
    /module/task.yml
    /flow/approval.yml

## Concept at Glance & Getting Started

Let's explore them by creating it from scratch simple lovely app: Task Approval app.

Endorphine is made 100% in Ruby, specifically in Ruby on Rails.
All components of Endorphine live in Rubygems. Let's install Endorphine
CLI core. By the way, Endorphine requires Ruby 2.7+. We recommend you use
version manager. Install rvm or rbenv.

Let's install Endorphine CLI core

    gem install endorphine
    
Let's create a new app

    endorphine create app TaskManager
    
Now let's inspect app.yml

    app: TaskManager
    title: Task Manager Application
    
## Installing a module

Open the Gemfile

    gem 'endorphine'
    gem 'endorphine-user'

Whoa you get a dashboard!

## Extending a module

    endorphine create module <YourGitHubAccount>/task

I will create my own

    endorphine create module mufid/endorphine-form
    
Now inspect the module

    # module.yml
    extends: endorphine/form
    endorphine:
      form:
        create:
          task:
            title:
              type: string
              validation: presence
            description:
              type: string
              validation: presence
            

Now push it to your own repository.

   gem 'endorphine-form', github: 'EndorphineSystems/approval-module'

### Module

A module is an installable and upgradeable within Endorphine.
Example of built-in module is UserModule. To use a module, you need
to install it. Install a module by putting it 
