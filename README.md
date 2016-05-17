Some simple utilities I've written to make using git more pleasant.

## git-multistatus

Print out a list of all heads relative to a provided baseline.  HEAD
has a *. Local commits are listed below the ref name. Each ref is
trailed by a number in parens which is the number of commits by which
it trails the baseline.

## git-smash

Stomps on the current commit metadata date and author (plus whatever
other args it has). A fine thing to do to a commit you've just patched
up and rebased on top of a bunch of newer history before you resubmit
it.

Like all history smashing, don't do this on things people already rely
on.
