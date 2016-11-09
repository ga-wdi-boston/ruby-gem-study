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

The gem that I decided to research is Resque; Resque is a Redis-backed library for creating background jobs, placing those jobs in multiple queues, and processing them later. So it seems like Resque is utilized to optimize job-processing capabilities. Background jobs handles by Resque include any Ruby class or module that responds to 'perform'. Resque is comprised of 3 parts:
1. A Ruby library fo creating, querying, and processing jobs.
2. A Rake task for starting a worker which processes jobs.
3. A Sinatra app for monitoring queues, jobs, and workers.

The gem that I found to compare against Resque is called DelayedJob. It seems like DeplayedJob's primary focus is to asynchronously execute longer tasks in the background. These tasks include but are not limited to: sending mass emails, image resizing, http downloads, updating collections, checking for spam, importing batchs, etc. So it DelayedJob is primarily concerned with handling tasks that require a large amount of processing time.

After a brief comparison, its clear that Resque is clearly the superior gem: it has the ability to queue the jobs (as DelayedJob does), but also allows users to assign "workers" to each job's processing and therefore gives the user a more dynamic toolset for processing. In addition, Resque also provides the user with superior job-processing-monitorability. The user is able to monitor jobs, queues, and workers with Resque. This would allow our team to optimize their job-processing and job-monitoring abilities in a more effective and efficient manner. 
```
