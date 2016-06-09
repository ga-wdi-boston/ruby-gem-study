As an exercise, pick one of the gems listed above and research it;
then, research some alternative gems, and pick the gem that you think
is the next best alternative. How might you justify this choice of best
alternative gem to a senior engineer on your team?

```txt
Capybara is an integrated testing tool that simulates how a user would interact
with your program.  It's designed to be used on top of a web based driver, and
depending on the application you're developing, you would want to adjust your
choice of driver, which seems to be the biggest thing developers consider when using
capybara, as opposed to picking an alternative gem.  For example rack::test is the
default one, and the fastest, but does not support JavaScript, so if your application
has JavaScript and jQuery in it, you would want to use a different driver like
selenium or env.js.  A viable alternative would be to use the Cucumber gem and the
Holy Grail or Akephalos. I would consider switching to this if the application we
needed to test has more JavaScript, or you wanted to more fully emulate the user
experience and drive a virtual browser session from action to action in your tests.
```
