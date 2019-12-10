Some simple utilities I've written to make using git more pleasant.

## git-all

Usage: `git all [--recursive] 'command'`

Finds every submodule and runs a command in it. Similar to
`git submodule foreach`, except it runs the commands in parallel.
Nice for io-blocking things. Stdout for each command is buffered
separately until all commands complete (stderr is not).

Example: `git all 'git fetch && git merge --ff-only origin/master'`

## git-multistatus

Usage: `git multistatus upstream-head...`

Print out a list of all refs/heads relative to a provided baseline.
HEAD has a *. Local commits are listed below the ref name. Each ref
is trailed by a number in parens which is the number of commits by
which it trails the baseline.

This is designed to be run in a terminal under watch.

Example: `git multistatus origin/master origin/branch/v2`

## git-smash

Stomps on the current commit metadata date and author (plus whatever
other args it has). A fine thing to do to a commit you've just patched
up and rebased on top of a bunch of newer history before you resubmit
it. Takes all arguments git commit --amend does.

Like all history smashing, don't do this on histories people already
rely on.

Example: `git commit -m "thing" ; touch foo; git add foo; git smash -a -C HEAD`
