This is a fork of the official [ruby-build](https://github.com/sstephenson/ruby-build) project for patches that are used internally by the Ruby agent team to build older Ruby versions to test against.

Specifically, this fork adds three new Ruby definitions for building old Ruby versions:

* 1.8.7-backports
* ree-backports
* 1.9.2-backports

Each one of these new defintions is identical to the latest patch-level in the series that it's based on, but with a patch for a [build issue](https://bugs.ruby-lang.org/issues/8384) backported from 1.9.3.

The referenced build issue makes it difficult to build these older Ruby versions against recent OpenSSL version, and the backported patch fixes this.

## Merging in changes from upstream

In order to pick up new Ruby build definitions, you'll want to periodically merge in changes from the upstream project.

To do this, first make sure you have an upstream remote pointing at the official repo:

```
git remote add upstream git@github.com:sstephenson/ruby-build.git
```

... and then fetch and merge into master and push your changes here:

```
git fetch upstream
git merge upstream/master
git push origin master
```
