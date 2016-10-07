---
layout: default
---

# Setup for CCSC Tutorial

## Prerequisites

-   Create a (free personal) [GitHub](https://github.com/)
    account.

-   Choose local setup:  Windows (10), OS X (with Homebrew),
    Linux (using Cloud9 VM).

## Windows (10)

## OS X (with Homebrew)

## Linux (Cloud9)

-   Create a (free) [Cloud9](https://c9.i0/) account.

-   Login, create a new workspace.  Under "Choose a template"
    pick "Blank" to get the default Ubuntu virtual machine.

-   In the terminal (lower right portion of workspace view)
    install [Bundler](http://bundler.io/) (using Ruby's `gem
    install` command):

    <pre>
    <span class="muted">user:~/workspace $</span> gem install bundler
    <span class="muted">Fetching: bundler-1.13.2.gem (100%)
    Successfully installed bundler-1.13.2
    1 gem installed</span>
    </pre>

    <!-- Other linux: should confirm Ruby version and install
    development tools if necessary. -->

-   Set up `git` and use it to
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
