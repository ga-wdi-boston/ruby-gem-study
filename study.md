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

Paperclip
(https://github.com/thoughtbot/paperclip)

Paperclip is well-documented ruby gem. Last commit was 10 days ago.

It has over 11 million downloads on rubygems.org. The last version of Paperclip gem was posted on July 1, 2016.

It is made by a company called thoughtbot. It is used for an easy file attachment.

Paperclip doesn't have any file processing abilities. It is mostly used for building simple APIs because they don't need processing. If we want to add processing abilities, Paperclip immigrates with a program called ImageMagick. ImageMagick is a image processor. It can covert images format, from PNG to JPEG and so on. It can also resize images and return images in the same format. It also allows drawing on an image, watermarks etc.

For example https://www.stockphoto.com/search/concept is one of the online gallery that isn't free. If we want to download an image that has a watermark on it, we can, but that isn't useful in case we want to use that image. If we buy an image, we can download a version without watermark. When someone upload an image, ImageMagick comes renders two images, and holds two different formats (with and without watermark) avaiable for download.

We need to install ImageMagick separately.

ImageMagick isn't always necessary. If we want only to upload an image and not to process it, ImageMagick isn't needed.



An alternatives to Paperclip is CarrierWave (https://github.com/carrierwaveuploader/carrierwave).

## Reasons for choosing CarrierWave over Paperclip

CarrierWave compared to Paperclip has processing capabilities and let's you choose the order of processing files. Files can be processed with many different processors. Those processors are powerful.

CarrierWave is also well documented and mainained gem. It has over 7 million downloads on rubygems.org


Both Paperclip and CarrierWave have advantages and disadvantages. Even though some of the recent issues that have been reported on CarrierWave Github page are related to the capabilities regarding image validation, CarrerWave seems better option because it allows image/files processing as well as generating thumbs on uploads, adding a single string image attribute for referencing the uploaded images, supports various storage backends etc.

There are other alternatives out there too. Dragonfly would be another alternative. 

We should choose gems depending on our needs. For example, if we don't need to process files/images than Paperclip can be a good option too.


```
