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
I did some research into RSpec, a Ruby gem that provides a testing framework for
Ruby projects. It has a deep library spanning four core gems within the project,
plus dependencies on a number of third-party gems.

All this content makes RSpec a powerful tool for test-driven development (TDD),
but it has downsides as well. Many developers lament RSpec's bloat problem,
complaining that it makes things "unecessarily complicated" (Sam Koblenski,
"RSpec or Minitest, How Does One Choose?"), providing too many ways to do the
same things. It essentially requires developers to learn a new, domain-specific
language (DSL), which can waste time when all you need to do is run a few simple
tests.

A number of sources pointed to Minitest as an optimal alternative. In comparison
to RSpec, Minitest is leaner and more self-contained. It has far fewer
dependencies on gems external to the core project, reducing concerns about
maintenance and stability. Where RSpec has a lot of its own ways of doing
things, making for a steep learning curve, Minitest "is just Ruby" (Brandon
Hilkert, "7 Reasons Why I'm Sticking With Minitest and Fixtures in Rails").
Minitest is a Ruby class and leans heavily on the core language that Ruby
developers already know, making it easy to get tests up and running.

It's worth noting that both RSpec and Minitest are well-maintained, with commits
on at least a monthly basis and a low ratio of open to closed issues.

While RSpec has a lot of power and a large community around it, Minitest is a
great alternative for a team with a lot of junior developers, a tight testing
schedule, or both. It's simpler, smaller, easier to understand, and perfectly
adequate for the vast majority of a team's TDD needs.
```
