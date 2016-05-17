Some simple utilities I've written to make using git more pleasant.

## git-multistatus

Print out a list of all heads relative to a provided baseline.  HEAD
has a *. Local commits are listed below the ref name. Each ref is
trailed by a number in parens which is the number of commits by which
it trails the baseline.
