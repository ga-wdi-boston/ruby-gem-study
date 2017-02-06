# Ruby Gem Study

Use your favorite search engine and the provided readings to research and
respond to the following questions.

In your responses, be sure to cite any relevant sources you consulted in your
search. We ask you to write responses in your own words in order to see how you
process what you've read. Please do not respond with direct quotes from source
material. Instead, digest what you've read and repeat it in your own voice.

## Required Readings

-   [RubyGems](https://en.wikipedia.org/wiki/RubyGems)
-   [Gemfiles](http://bundler.io/gemfile.html)

## What Is a Gem?

A **gem** is a library of Ruby code that you can incorporate into your projects.
Using an external library allows you to benefit from someone else's work, so
that you don't need to waste time reinventing the wheel.

Here are some gems that commonly appear in Ruby and Ruby on Rails projects:

| Gem | Description |
| --- | --- |
| [bcrypt](https://rubygems.org/gems/bcrypt) | Secure hash algorithm. |
| [capybara](https://rubygems.org/gems/capybara) | Integration testing tool for rack-based web applications. |
| [devise](https://rubygems.org/gems/devise) | Authentication for Ruby on Rails. |
| [httparty](https://rubygems.org/gems/httparty) | RESTful web services client. |
| [paperclip](https://rubygems.org/gems/paperclip) | Upload management for ActiveRecord. |
| [pry-byebug](https://rubygems.org/gems/pry-byebug) | A combination of two separate gems, `pry` and `byebug` |
| [resque](https://rubygems.org/gems/resque) | Redis-backed library for creating background jobs. |
| [rspec](https://rubygems.org/gems/rspec) | Behavior-driven development suite. |
| [rubocop](https://rubygems.org/gems/rubocop) | Linter for Ruby. |
| [scss_lint](https://rubygems.org/gems/scss_lint) | Linter for SASS/SCSS. |


The jobs these gems do can range from debugging to testing to integrating into
an API.

## Installing Ruby Gems

There are two main ways to install Ruby gems. The first is manually, through the
command line:

`gem install resque`

This will download and install the gem that you specify.  In this case it's the
`resque` gem.

The second way is to use `bundler` (another gem, which we installed during
install-fest) and a 'Gemfile', a file containing a list of gems that our project
requires. To install the gems listed on a Gemfile, navigate to the location of
the Gemfile and run

`bundle install`

> When you run `bundle install` for the first time in a project, a new file called 'Gemfile.lock' gets created. This file constrains the versions of the different gems used, so that even if `bundle install` is re-run, and some gems have been updated, only the versions specified in Gemfile.lock get used.

There are a lot of similarities between Node modules and Ruby gems.

| Node Module | Ruby Gem |
| :---------: | :------: |
| npm install _moduleName_ | gem install _gem_\__name_ |
| npm install | bundle install |
| package.json | Gemfile |

However, there are a couple of differences too. For instance, Node modules
(except when using the `-g` flag) get installed within a particular project,
inside of a directory called `node_modules`. Ruby gems, in contrast, will not be
installed within the project.

### Your Turn :: Installing Ruby Gems

Run `bundle install` command above from within the repo. Then, just for fun, run
`gem install bundler` and look at the output you get.

## Researching Gems

### Where Can I Find Ruby Gems?

The two main places to look for Ruby gems are
**[RubyGems.org](https://rubygems.org)** and
**[The Ruby Toolbox](https://www.ruby-toolbox.com/)**. RubyGems.org is the
official listing place for all published gems, and it's the place that our gems
actually come from when we install them. The Ruby Toolbox, in contrast, doesn't
actually have the code on its site, but it provides some additional information
about gems that's not available on RubyGems.org, including grouping gems by
category.

### Which Gems Should I Use?

There will often be multiple gems that can be used for the same purpose. How can
we choose between them? Ultimately, we want to use code that is well-maintained,
well-tested, and well-documented. If there's a link to the source code on
GitHub, that can be a great place to find things like:

-   When the last commit was, and how frequently commits are made.
-   How many outstanding issues there are (total and as a % of all issues).
-   Who the collaborators are.
-   If there are tests (usually found in the `/test` or `/spec` directory) and
    how extensive they are.

Depending on the gem, there may not necessarily be a lot of documentation
available, but if the GitHub project has a wiki set up, that can be a good place
to find information. Additionally, many gems have official 'rdoc' documentation;
there's a searchable web interface for that documentation at
**[RubyDoc.info](http://rubydoc.info)**.

## Gems and Alternatives

As an exercise, pick one of the gems listed above and research it; then,
research some alternative gems, and pick the gem that you think is the next best
alternative. How might you justify this choice of best alternative gem to a
senior engineer on your team? Explain this below and submit a pull request.
```md
GEM
  remote: https://rubygems.org/
  specs:
    actionpack (4.2.7.1)
      actionview (= 4.2.7.1)
      activesupport (= 4.2.7.1)
      rack (~> 1.6)
      rack-test (~> 0.6.2)
      rails-dom-testing (~> 1.0, >= 1.0.5)
      rails-html-sanitizer (~> 1.0, >= 1.0.2)
    actionview (4.2.7.1)
      activesupport (= 4.2.7.1)
      builder (~> 3.1)
      erubis (~> 2.7.0)
      rails-dom-testing (~> 1.0, >= 1.0.5)
      rails-html-sanitizer (~> 1.0, >= 1.0.2)
    activemodel (4.2.7.1)
      activesupport (= 4.2.7.1)
      builder (~> 3.1)
    activesupport (4.2.7.1)
      i18n (~> 0.7)
      json (~> 1.7, >= 1.7.7)
      minitest (~> 5.1)
      thread_safe (~> 0.3, >= 0.3.4)
      tzinfo (~> 1.1)
    addressable (2.5.0)
      public_suffix (~> 2.0, >= 2.0.2)
    bcrypt (3.1.11)
    builder (3.2.3)
    byebug (8.2.5)
    capybara (2.12.0)
      addressable
      mime-types (>= 1.16)
      nokogiri (>= 1.3.3)
      rack (>= 1.0.0)
      rack-test (>= 0.5.4)
      xpath (~> 2.0)
    climate_control (0.1.0)
    cocaine (0.5.8)
      climate_control (>= 0.0.3, < 1.0)
    coderay (1.1.1)
    devise (3.5.10)
      bcrypt (~> 3.0)
      orm_adapter (~> 0.1)
      railties (>= 3.2.6, < 5)
      responders
      thread_safe (~> 0.1)
      warden (~> 1.2.3)
    diff-lcs (1.3)
    erubis (2.7.0)
    i18n (0.8.0)
    json (1.8.6)
    loofah (2.0.3)
      nokogiri (>= 1.5.9)
    method_source (0.8.2)
    mime-types (3.1)
      mime-types-data (~> 3.2015)
    mime-types-data (3.2016.0521)
    mimemagic (0.3.0)
    mini_portile2 (2.1.0)
    minitest (5.10.1)
    nokogiri (1.7.0.1)
      mini_portile2 (~> 2.1.0)
    orm_adapter (0.5.0)
    paperclip (4.3.7)
      activemodel (>= 3.2.0)
      activesupport (>= 3.2.0)
      cocaine (~> 0.5.5)
      mime-types
      mimemagic (= 0.3.0)
    pry (0.10.4)
      coderay (~> 1.1.0)
      method_source (~> 0.8.1)
      slop (~> 3.4)
    pry-byebug (3.3.0)
      byebug (~> 8.0)
      pry (~> 0.10)
    public_suffix (2.0.5)
    rack (1.6.5)
    rack-test (0.6.3)
      rack (>= 1.0)
    rails-deprecated_sanitizer (1.0.3)
      activesupport (>= 4.2.0.alpha)
    rails-dom-testing (1.0.8)
      activesupport (>= 4.2.0.beta, < 5.0)
      nokogiri (~> 1.6)
      rails-deprecated_sanitizer (>= 1.0.1)
    rails-html-sanitizer (1.0.3)
      loofah (~> 2.0)
    railties (4.2.7.1)
      actionpack (= 4.2.7.1)
      activesupport (= 4.2.7.1)
      rake (>= 0.8.7)
      thor (>= 0.18.1, < 2.0)
    rake (12.0.0)
    responders (2.3.0)
      railties (>= 4.2.0, < 5.1)
    rspec (3.5.0)
      rspec-core (~> 3.5.0)
      rspec-expectations (~> 3.5.0)
      rspec-mocks (~> 3.5.0)
    rspec-core (3.5.4)
      rspec-support (~> 3.5.0)
    rspec-expectations (3.5.0)
      diff-lcs (>= 1.2.0, < 2.0)
      rspec-support (~> 3.5.0)
    rspec-mocks (3.5.0)
      diff-lcs (>= 1.2.0, < 2.0)
      rspec-support (~> 3.5.0)
    rspec-support (3.5.0)
    slop (3.6.0)
    thor (0.19.4)
    thread_safe (0.3.5)
    tzinfo (1.2.2)
      thread_safe (~> 0.1)
    warden (1.2.7)
      rack (>= 1.0)
    xpath (2.0.0)
      nokogiri (~> 1.3)

PLATFORMS
  ruby

DEPENDENCIES
  capybara (~> 2.5)
  devise (~> 3.5, >= 3.5.2)
  paperclip (~> 4.3, >= 4.3.1)
  pry-byebug (~> 3.3.0)
  rspec (~> 3.3)

RUBY VERSION
   ruby 2.3.1p112

BUNDLED WITH
   1.13.7
```
```md
selenium-webdriver is the next most popular browser testing gem after capybara. 
It appears to have better automation features and its updated on a monthly basis.
18% of all issues are still open, thats 390 out os 2121 closed.

Researching this was a bit tricky to really understand what they do and how to use them. I will continue to read up on the material to get more familiar with it.

I also installed the gem to see what it would  look like. Not sure if I was supposed to that or not, however I will not be staging or commiting it, I don't want to break anything.


```
