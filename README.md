About this repo
===============

This repo is intended to hold some Ansible playbooks and roles to build my
development environments with Vagrant. At time of this writing, only a Ruby on
Rails role exists.

rails-dev role
==============

This role turns a Debian/Ubuntu machine into an environment to develop Ruby web
applications (Ruby on Rails, Sinatra, etc.).

It includes:

* Some basic tools as [tmux](http://tmux.sourceforge.net/),
  [Vim](http://www.vim.org/), [GNU Emacs](http://www.gnu.org/s/emacs/),
  [Git](http://git-scm.org/) and [Zsh](http://zsh.org/).
* [chruby](https://github.com/postmodern/chruby) and
  [ruby-install](https://github.com/postmodern/ruby-install) to manage
  [Ruby](http://ruby-lang.org/) versions (also the last 2.1.x available version
  is installed).
* [PostgreSQL](http://postgresql.org/) including development libraries. A user
  called `rails` with password `vagrant` is also set up.
* [SQLite](http://www.sqlite.org/) including development libraries.
* [PhantomJS](http://phantomjs.org/) to drive integration tests without X.
* [Xvfb](http://www.x.org/archive/X11R7.7/doc/man/man1/Xvfb.1.xhtml), so you
  can use [Firefox](http://firefox.org/) or [Webkit](https://www.webkit.org/)
  in your tests. It also adds a `xvfb` service so it's enabled during boot
  time.  These tools are not installed by default.
* Some packages as `libxslt1-dev` or `libxml2-dev` that are useful to
  build some gems.

You can enable/disable or tweak the installation of those tools by settings
some variables.  The files on `vars` directories are self-explanatory. A file
in `host_vars` is the right place to override default variables.

Usage
=====

These playbooks are known to work on Debian "Wheezy" and Ubuntu Trusty.

If you're using Vagrant, you could rely on the Vagrantfile included in this repository.
Just set the `config.vm.box` parameter and try to bring up a machine:

    vagrant up rails

Now it's time to grab a coffee, a beer or whatever you like the most. And good
luck!

Disclaimer
==========

I've written this playbooks in a "works for me" fashion :). It's also the first
time I use Ansible and I fear that I've not followed the best practices.
