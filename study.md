# Ruby Gem Study

## What is a Gem?

A **gem** is a library of Ruby code that you can incorporate into your projects. Using an external library allows you to benefit from someone else's work, so that you don't need to waste time reinventing the wheel.

Here are a couple of gems that commonly appear in Ruby and Rails projects:

- `devise`
- `paperclip`
- `resque`
- `rspec`
- `capybara`
- `pry-byebug` (a combination of two separate gems, `pry` and `byebug`)

The jobs these gems do can range from debugging to testing to integrating into an API.

## Installing Ruby Gems

There are two main ways to install Ruby gems. The first is manually, through the command line:

`gem install resque`

This will download and install the gem that you specify.

The second way is to use `bundler` (another gem, which we installed during install-fest) and a 'Gemfile', a file containing a list of gems that our project requires. To install the gems listed on a Gemfile, navigate to the location of the Gemfile and run

`bundle install`

> When you run `bundle install` for the first time in a project, a new file called 'Gemfile.lock' gets created. This file constrains the versions of the different gems used, so that even if `bundle install` is re-run, and some gems have been updated, only the versions specified in Gemfile.lock get used.

There are a lot of similarities between Node modules and Ruby gems.

| Node Module | Ruby Gem |
| :---------: | :------: |
| npm install _moduleName_ | gem install _gemName_ |
| npm install | bundle install |
| package.json | Gemfile |

However, there are a couple of differences too. For instance, Node modules (except when using the `-g` flag) get installed within a particular project, inside a folder called `node_modules`. Ruby gems, in contrast, will not be installed within the project.

### Your Turn :: Installing Ruby Gems

Run `bundle install` command above from within the repo. Then, just for fun, run `gem install bundler` and look at the output you get.

## Researching Gems

### Where Can I Find Ruby Gems?

The two main places to look for Ruby gems are **[RubyGems.org](https://rubygems.org)** and **[The Ruby Toolbox](https://www.ruby-toolbox.com/)**. RubyGems.org is the official listing place for all published gems, and it's the place that our gems actually come from when we install them. The Ruby Toolbox, in contrast, doesn't actually have the code on its site, but it provides some additional information about gems that's not available on RubyGems.org, including grouping gems by category.

### Which Gems Should I Use?

There will often be multiple gems that can be used for the same purpose. How can we choose between them? Ultimately, we want to use code that is well-maintained, well-tested, and well-documented. If there's a link to the source code on GitHub, that can be a great place to find things like:

- [ ] When the last commit was, and how frequently commits are made.
- [ ] How many outstanding issues there are (total and as a % of all issues).
- [ ] Who the collaborators are.
- [ ] If there are tests (usually found in the `/test` or `/spec` directory) and how extensive they are.

Depending on the gem, there may not necessarily be a lot of documentation available, but if the GitHub project has a wiki set up, that can be a good place to find information. Additionally, many gems have official 'rdoc' documentation; there's a searchable web interface for that documentation at **[RubyDoc.info](http://rubydoc.info)**.

As an exercise, pick one of the gems listed above and research it; then, research some alternative gems, and pick the gem that you think is the next best alternative. How might you justify this choice of best alternative gem to a senior engineer on your team? Explain this below and submit a pull request.

```txt
Devise.
  This is an authentication solution for Rails based on Warden, which is designed to provide a common authentication of multiple Ruby Rack web applications.  Rack is a interface that wraps HTTP client server requests into one arguement, which returns an array of status, headers, and body.  Warden works right after the Rack stack, where the request information is stored.  Warden verifies the identity of a loggin in user with a session string, where a disguised user id is stored.  Warden will then store authentication information and allow all downstream applications to share this single authentication object, as well as handling users that are not logged in.

  Devise was created to allow users to quickly develop and application that uses authentication.  It creates all the code and routes required to create accounts, log in, log out.  Devise consists of 10 modules:
  Database Authenticatable, which will store an encrypted password to authenticate a user.
  Confirmable, that sends emails with confirmation instructions and cofirms that account exists during sign in.
  Recoverabe resets the user password.
  Registerable handles signing up users.
  Rememberable manages generating and clearing tokens for remembering a user, which is stored as a cookie.
  Trackable stores sign-in count, timestamps, and IP address.
  Timeoutable will expire a session that has not been active within a period of time.
  Validatable validates email and password data.
  Lockable will lock an account after a specified number of failed attempts to gain access.

  The best alternative is OmniAuth, designed to be as minimally impacting on a applications with multiple authentication providers.  Using OmniAuth, we have more options available with authentication providers, whereas with Devise, we would only be able to work under the Warden protocol.  OmniAuth can be connected to almost any system, and there are hundreds of providers (facebook, twitter) with which we can build a  developer strategy.  There is a OmniAuth::Form, which is a simple form builder that can be used to prompt the user for authentication information.  The main goal of all of this is to remove the need for a end user to have many different passwords for different providers; instead, they can authenticate through a facebook, twitter, etc account, and be authenticated for the website.
  OmniAuth has made over 1100 commits and has been downloaded over 9.2 million times.  It's popular because of the ease with which any type of website can use authentication with major providers, such as facebook, Twitter, Dropbox, Amazon, Google, and hundreds more.


```
