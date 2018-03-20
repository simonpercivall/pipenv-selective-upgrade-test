# Setup

Basic pipenv project with two listed dependencies:

* `more-itertools == "*"` with lockfile at 4.0.0 (latest 4.1.0)
* `sqlalchemy-utils == "*"`, at (currently) latest

The lockfile contains outdated dependencies for those two libraries:

* `sqlalchemy` at 1.1.18 (latest 1.2.5)
* `six` at 1.7.0 (latest 1.11.0)

# Updating

* `pipenv update more-itertools` updates the installed package, but
  _doesn't_ update the lockfile, and doesn't update any dependencies.

* `pipenv install --selective-upgrade six` adds `six` as a new
  dependency, and updates _all_ packages in the lockfile, i.e.
  `sqlalchemy-utils`, `more-itertools`, and all their dependencies.
