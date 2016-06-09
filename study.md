As an exercise, pick one of the gems listed above and research it;
then, research some alternative gems, and pick the gem that you think
is the next best alternative. How might you justify this choice of best
alternative gem to a senior engineer on your team?

```txt
I researched the devise gem.  It's an authentication gem that allows
programmers to securely store, retrieve and update password information.  Allows
for destruction of accounts by users.  It can timeout, lock an account, among
other functionality.  This gem has fairly good documentation and the last commit
to the Github repo was 13 days ago.

Oauth2 may be a better solution for us to use, though.  It's well tested, has
robust functionality, and it can be used on Ruby v.0 or high.  Devise requires
2.1.0 at least.  So, we have more flexibility with the versions of Ruby that we
can use.
```
