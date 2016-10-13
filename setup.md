---
title: Setup
section: 1
layout: default
summary:
    "Set up the software you need, and confirm that it's set up correctly."
---

# Setup

...for GitHub Pages tutorial, CCSC-Eastern fall 2016 conference.

## Prerequisites

Create a (free personal) [GitHub](https://github.com/) account.
Choose environment for local[^local] setup:  [Linux (on Cloud9)](#linux-on-cloud9),
[Windows (10)](#windows-10), or [OS X (with Homebrew)](#os-x-with-homebrew).

[^local]: "Local," i.e., not the setup hosted by GitHub.  This is
    here mostly to remind me to talk about footnotes :)

## Linux (on Cloud9)

Use this setup if you want to avoid installing any new software on
your computer.  (Or, if you have Linux on your computer, use these
instructions, modified as necessary for your distribution.)

1.  Create a (free) [Cloud9](https://c9.i0/) account.  Login and create
    a new workspace.  Under "Choose a template,"
    pick "Blank" to get the default [Ubuntu](https://www.ubuntu.com)
    Linux configuration.

3.  In the terminal (lower right section of the initial Cloud9 workspace
    view), set up [Git](https://git-scm.com) and use it to
    make a local copy of the example repository I created for
    this tutorial:

    <pre>
    <span class="muted">user:~/workspace $</span> git config --global user.name "YOUR NAME"
    <span class="muted">user:~/workspace $</span> git config --global user.email "YOUR EMAIL ADDRESS"
    <span class="muted">user:~/workspace $</span> git clone 'https://github.com/dvon/ccsc-example'
    <span class="muted">Cloning into 'ccsc-example'...
    remote: Counting objects: 52, done.
    remote: Compressing objects: 100% (31/31), done.
    remote: Total 52 (delta 15), reused 43 (delta 10), pack-reused 0
    Unpacking objects: 100% (52/52), done.
    Checking connectivity... done.</span>
    </pre>
    
    *Note: If you are setting this up on a different Linux distribution,
    you may need to install Git for this step to work; you may also need
    to install Ruby (at least version 2.x.x) and the Ruby development
    tools for steps 3 and 4 to work.*

4.  Install [Bundler](http://bundler.io/) (using
    [Ruby](https://www.ruby-lang.org/)'s `gem install` command):

    <pre>
    <span class="muted">user:~/workspace $</span> gem install bundler
    <span class="muted">Fetching: bundler-1.13.2.gem (100%)
    Successfully installed bundler-1.13.2
    1 gem installed</span>
    </pre>

5.  Navigate to the repository folder; use Bundler to update Ruby
    packages (based on contents of repository's "Gemfile") needed
    for local [Jekyll](https://jekyllrb.com) installation:

    <pre>
    <span class="muted">user:~/workspace $</span> cd ccsc-example
    <span class="muted">user:~/workspace/ccsc-example (master) $</span> bundle update
    <span class="muted">Fetching gem metadata from https://rubygems.org/...........
    Fetching version metadata from https://rubygems.org/..
    Fetching dependency metadata from https://rubygems.org/.
    Resolving dependencies...</span>
    </pre>

6.  Execute Jekyll's `serve` command via Bundler's `exec` command,
    with host and port arguments suitable for Cloud9 environment:
    
    <pre>
    <span class="muted">user:~/workspace/ccsc-example (master) $</span> bundle exec jekyll serve -H 0.0.0.0 -P 8080
    <span class="muted">Configuration file: /home/ubuntu/workspace/ccsc-example/_config.yml
                Source: /home/ubuntu/workspace/ccsc-example
           Destination: /home/ubuntu/workspace/ccsc-example/_site
     Incremental build: disabled. Enable with --incremental
          Generating... 
                        done in 0.401 seconds.
     Auto-regeneration: enabled for '/home/ubuntu/workspace/ccsc-example'
    Configuration file: /home/ubuntu/workspace/ccsc-example/_config.yml
        Server address: http://0.0.0.0:8080/ccsc-example/
      Server running... press ctrl-c to stop.</span></pre>

    Just after you run this command in the Cloud9 terminal, you should see
    a small window pop up with a "Your code is running at..." link.  Click
    the link.

    You'll get a "/ not found" error at first.   You just need
    to add `/ccsc-example/` to the end of the URL, so that it's something like
    `https://workspace-user.c9users.io/ccsc-example/`, and then refresh
    the page.  If everything's worked correctly, you should see a page
    titled "CCSC Example" with a few titles, a list, a little bit of source
    code and a little bit of mathematical notation.

    *Note: If you're running this on your own local Linux installation,
    rather than on Cloud9, you don't need to specify host and port
    arguments.  And you can just use the URL Jekyll gives you, right
    after "Server address," near the end of the output you get when
    you run the `serve` command.*

## Windows (10)

Coming soon...

## OS X (with Homebrew)

Coming soon...
