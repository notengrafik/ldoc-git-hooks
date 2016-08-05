LDoc Git hooks
==============

This code is useful for projects that use both Git and
[LDoc](https://github.com/stevedonovan/LDoc/). It automatically builds
and commits documentation after each commit (it amends the commit to
add the documentation). It reports errors in the LDoc annotations and
lets the user decide whether to abort the commit to fix the problems or
not.

Requirements
------------

Currently [Zenity](https://help.gnome.org/users/zenity/stable/) is
used for reporting errors because [known methods for reading keyboard
input in a hook script](
http://stackoverflow.com/questions/3417896#10015707) don't work when
using `git gui`. Zenity therefore needs to be installed and restricts the
`post-commit` hook in its current form to Linux with a GUI. However, it
can easily be modified to use other means of interaction. Contributions,
especially ones making the error feedback more general-purpose, are
always welcome.

It is assumed that there is a `config.ld` file in the root directory of
the Git repository (see the [documentation for `config.ld`](
https://github.com/stevedonovan/LDoc/blob/master/doc/doc.md#user-content-fields-allowed-in-configld)).

The files `pre-commit` and `post-commit` need to be copied to the
directory `.git/hooks`.
