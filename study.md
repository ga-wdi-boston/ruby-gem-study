As an exercise, pick one of the gems listed above and research it;
then, research some alternative gems, and pick the gem that you think
is the next best alternative. How might you justify this choice of best
alternative gem to a senior engineer on your team?

```txt
Gem: Capybara.

Capybara is a ruby gem that autmates functional testing of a websites functionality.
The gem mimicks language of an actual user by simulating user story scenarios.

Once the page is loaded, Capybara locates a specific element on the DOM and executes a relevant action such as a link or button click.

This is an example of code that would mimick a user profile input:

describe 'UserRegistration' do
   it 'allows a user to register' do
     visit new_user_registration_path
     fill_in 'First name', :with => 'New'
     fill_in 'Last name', :with => 'User'
     fill_in 'Email', :with => 'newuser@example.com'
     fill_in 'Password', :with => 'userpassword'
     fill_in 'Password Confirmation', :with => 'userpassword'
     click_button 'Register'
     page.should have content 'Welcome'
   end
 end

 and this is an example of code on how the element on the DOM is located to perform such as action:

 Capybara.add_selector(:my_selector_area) do
  xpath { "actual_xpath" }
end

within(:my_selector_area) do
  fill_in 'Name', :with => 'John'
  fill_in 'Email', :with => 'john@doe.com'
end

This is the best overall gem to test the functionality of a website as it is recommended for its great speed. The one pitfall is that it lacks the ability to run javascript but it has a complementary Selenium gem to test the js.

```
