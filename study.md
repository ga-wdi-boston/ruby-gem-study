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
paperclip: Easy upload management for ActiveRecord
Paperclip is a plugin for Ruby on Rails’ ActiveRecord that lets files work as simply as any other attributes do. There are no extra database tables, only one library to install for image processing, and the ease of being able to refer to your files as easily as you refer to your other attributes
I found the info below on Paperclip and two alternatives, CarrierWave and Refile.
Paperclip
Paperclip falls short when it comes to file caching and keeping your code clean. And it isn't very well maintained.

Settings can be configured globally or on per model basis, which in turn puts a lot of logic that isn’t related to your model in your model. A side effect of this approach is that uploader logic can’t be tested independently of your model’s logic. And it basically has no file processing abilities. Ease-of-use and simplicity are Paperclip’s strong points.

When to use: It’s the go-to solution if you just need to upload a file and forget about it. It's also good enough when building simple APIs since they don't need file caching or processing. But it should be avoided in more complex applications.

CarrierWave
CarrierWave is the Swiss army knife of Rails image uploaders.

It stores all uploader logic in uploader classes, which keeps your code clean, reusable and easy to test! Such code organization enables the definition of custom file processors which can use any kind of third party library, be it a gem or shell command.

It's most efficient when it comes to image processing as it lets you choose the order of processing files.

Files can be processed with many different processors and new processors can be defined. These processors are not only useful for creating images of different sizes, but they can also be used for extracting EXIF data, parsing uploaded text files, validating uploaded files... You are limited only by your imagination.

When to use: CarrierWave should be used in applications that are ‘image heavy’ or have logic associated with files that get uploaded.

Refile
Refile is the newest of the three, a successor to the ‘over-engineered’ CarrierWave, and strikingly similar to Dragonfly. It tries to combine the ease-of-use and simplicity of Paperclip with the power of CarrierWave. And falls short at doing that, at least in my opinion.

It has the ability to define custom file processors, but it processes all files on-the-fly. An interesting concept as it makes the gem basically unusable in production environments without a CDN and can be a potential vulnerability to DoS attacks.

It mounts as a separate Sinatra application on top of your Rails application, which enables it to stream files to improve page render times and conserve server memory.

Customization is a pain and testing isn’t the easiest task either as the application can’t tell you where it stored the file you gave it. On the other hand, it’s rapidly changing and has a lot of supporters.

When to use: In my opinion, on-the-fly image processors should be avoided as they have inherited DoS problems, no matter if your app uses a CDN or not. Refile should only be used if you absolutely need on-the-fly image resizing.
Overview
Feature	               Paperclip	          CarrierWave	          Refile
CDN support	            Minimal	                OK	                OK
File processing	         None	               Extensive	          Minimal
Image processing	       Yes	               Extensive	            Yes
Dynamic image resizing	  No	                  No	                Yes
File streaming	          No	                  No	                Yes
Customizability	        Simple	             Extensive	            None

Conclusion
Choosing between CarrierWave, Paperclip and Refile can be difficult at times, but I would always recommend CarrierWave. It is the most powerful and customizable of the three. It keeps your code organized and clean, and is easy to test.

Refile isn't ready for prime time yet as it is still experiencing growth pains and has DoS issues, and Paperclip is fairly simplistic.
```
