# rsync-netbsd-cvs -- a script to mirror the NetBSD CVS repository and update local directories

Copyright (c) 2019 by Greg A. Woods <woods@planix.ca>

This work is licensed under the Creative Commons Attribution-ShareAlike
4.0 International License.

## Introduction

`rsync-netbsd-cvs` is a script that can be used to regularly `rsync` the
CVS repository from NetBSD and also update a set of local working
directories.

## Installation

Just copy it somewhere such as a local `bin` or `libexec` directory and
run it, probably as a unique unprivileged user (e.g. `syssup`), possibly
regularly through `cron(8)`.

## Additional Features

There are two possibly useful options, plus a test and debug flag:

* `-d` enable debugging features
* `-l` just create "local directories" in the repository mirror
* `-r` just do the `rsync` step

Local directories are specified in a list of files each possibly
containing a list of directory pathnames.  These directories will be
created in the repository mirror, normally after each `rsync` (as they
don't exist in the remote master repository).  This helps you see
locally added things in local CVS working directories.
