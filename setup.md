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

-   Create a (free personal) [GitHub](https://github.com/)
    account.

-   Choose environment for local[^local] setup:  Linux (on Cloud9),
    Windows (10), OS X (with Homebrew).

[^local]: "Local," i.e., not the setup hosted by GitHub.  This is
    here mostly to remind me to talk about footnotes :)

## Linux (Cloud9)

-   Create a (free) [Cloud9](https://c9.i0/) account.

-   Login, create a new workspace.  Under "Choose a template"
    pick "Blank" to get the default [Ubuntu](https://www.ubuntu.com)
    Linux configuration.

-   In the terminal, set up [Git](https://git-scm.com) and use it to
    make a local copy of the example repository I created for
    this tutorial:

    <pre>
    <span class="muted">user:~/workspace $</span> git config --global user.name "YOUR NAME"
    <span class="muted">user:~/workspace $</span> git config --global user.email "YOUR EMAIL ADDRESS"
    <span class="muted">user:~/workspace $</span> git clone 'https://github.com/dvon/ccsc-example'
    <span class="muted">Cloning into 'ccsc-example'...
    remote: Counting objects: 3, done.
    remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
    Unpacking objects: 100% (3/3), done.
    Checking connectivity... done.</span>
    </pre>
    
    *Note: If you are setting this up on a different Linux distribution,
    you may need to install Git for this step to work; you may also need
    to install Ruby (at least version 2.x.x) and the Ruby development
    tools for the next step to work.*

-   Install [Bundler](http://bundler.io/) (using
    [Ruby](https://www.ruby-lang.org/)'s `gem install` command):

    <pre>
    <span class="muted">user:~/workspace $</span> gem install bundler
    <span class="muted">Fetching: bundler-1.13.2.gem (100%)
    Successfully installed bundler-1.13.2
    1 gem installed</span>
    </pre>

-   Navigate to the repository folder; use Bundler to update Ruby
    packages (based on contents of repository's `Gemfile`) needed
    for local [Jekyll](https://jekyllrb.com) installation:

    <pre>
    <span class="muted">user:~/workspace $</span> cd ccsc-example
    <span class="muted">user:~/workspace/ccsc-example (master) $</span> bundle update
    <span class="muted">Fetching gem metadata from https://rubygems.org/...........
    Fetching version metadata from https://rubygems.org/..
    Fetching dependency metadata from https://rubygems.org/.
    Resolving dependencies...</span>
    </pre>

-   
