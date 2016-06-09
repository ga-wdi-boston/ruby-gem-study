As an exercise, pick one of the gems listed above and research it;
then, research some alternative gems, and pick the gem that you think
is the next best alternative. How might you justify this choice of best
alternative gem to a senior engineer on your team?

```txt

The paperclip gem facilitates file uploads and catalogs on the server. Its easy of use
and simplicity are its strengths, however, in terms of its shortcomings, paperclip
falls in two specific areas: file caching and code organization.

When it comes the former, it is best user experience practice to avoid a situation
where the user is forced to choose his file again and upload it again after a form fails to validate.

The latter is a point worth mentioning because the settings in paperclip can be configured globally, affecting
the uploader logic insofar as putting unrelated logic into your model. Uploader logic cannot
be tested independently of one's model logic.

The next best alternative to the paperclip gem is CarrierWave. This particular gem addresses
the need for clean, reusable and testable code because it stores uploader logic in uploader classes.
It is also the most efficient for image processing as it enables you to choose the order of files.
The files can be processed with many different processors and new processors can be defined.  

```
