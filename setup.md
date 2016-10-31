---
title: Setup
section: 1
layout: default
summary:
    "Set up the software you need, and confirm that it's set up correctly."
---

# Setup

These instructions walk you through the process needed to setup
a local copy of an example site and then to run a local web server
and confirm that everything's working correctly.

## Prerequisites

Create a (free personal) [GitHub](https://github.com/) account.
Choose environment for local setup:

-   [Linux](#linux) (tested in Ubuntu 14.04, via Cloud9 web-based
    virtual machine).
-   [Windows](#windows) (tested in Windows 10).
-   [OS X](#os-x) (tested in Sierra).

## Linux

1.  Create a (free) [Cloud9](https://c9.io/) account.[^cloud9]  Login and create
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
    <span class="muted">user:~/workspace $</span> git clone https://github.com/dvon/ccsc-example
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

## Windows

1.  Download and install the latest version of [Git](https://git-scm.com)
    for Windows.  The installation wizard that pops up gives you a lot of
    options.  My notes below assume you want the minimal installation
    necessary for this tutorial,
    but it's fine for you to choose additional features you're interested
    in.
    
    -   When you get to "Select Components,"
        you can safely uncheck all of the options.  When you get to "Select
        Start Menu Folder" it's save to check "Don't create a Start Menu
        folder."

    -   When you get to "Adjusting your PATH environment, I suggest
        you leave the default, "Use Git from the Windows Command Prompt,"
        selected.  This will save you from having to modify the
        PATH environment variable via Windows settings later.
    
    -   When you get to "Configuring the line ending conversions," leave
        the first option, "Checkout Window-style, commit Unix-style line
        endings," selected.  As part of the tutorial you'll be
        downloading text files I created in Linux; this option will
        fix the line endings for you when you open these files in
        Windows.
    
    -   When you get to "Configuring the terminal emulator to use with
        Git Bash, it's save to choose "Use Windows' default console
        window."    
    
    -   Under "Configuring extra options," it's safe to uncheck both
        "Enable file system caching" and "Enable Git Credential Manager."

2.  Within the Windows Command Prompt (cmd.exe), setup Git and use it to
    make a local copy of the example repository I created for this
    tutorial.  (I created a folder called "ccsc" and put the repository
    copy in that folder.)
    
    <pre>
    <span class="muted">C:\Users\User Name></span>git config --global user.name "YOUR NAME"
    <span class="muted">C:\Users\User Name></span>git config --global user.email "YOUR EMAIL ADDRESS"
    <span class="muted">C:\Users\User Name></span>mkdir ccsc
    <span class="muted">C:\Users\User Name></span>cd ccsc
    <span class="muted">C:\Users\User Name\ccsc></span>git clone https://github.com/dvon/ccsc-example
    <span class="muted">Cloning into 'ccsc-example'...
    remote: Counting objects: 52, done.
    remote: Total 52 (delta 0), reused 0 (delta 0), pack-reused 52
    Unpacking objects: 100% (52/52), done.</span>
    </pre>

3.  Download and install [Ruby](https://www.ruby-lang.org/en/).  The
    easiest way to do this on Windows is to use
    [RubyInstaller](http://rubyinstaller.org).  The RubyInstaller
    site recommends using a 2.2.X installer; you probably want
    Ruby 2.2.5 (x64) (from
    [http://rubyinstaller.org/downloads](http://rubyinstaller.org/downloads)).
    When you run the installer, and get to "Installation
    Destination and Optional Tasks," select "Add Ruby executables
    to your PATH."  (And change the installation folder if you
    like.)
    
    In addition to Ruby, you need the
    [Development Kit](https://github.com/oneclick/rubyinstaller/wiki/Development-Kit) ("DevKit")
    in order to compile
    native extensions for some of the Ruby packages we'll need later
    on.  You probably want the download under "For use with Ruby
    2.0 and above (x64 - 64bits only)," on the left side near the
    bottom of the RubyInstaller download page.

    The Development Kit download is a self-extracting archive.
    Unfortunately, when you extract it you get a bunch of
    folders and files, rather than a single folder (containing
    a bunch of folders and files).  With that in mind, create
    a new folder and copy the downloaded file into it before you
    double-click on it to extract the files.
    Next, move the new folder (into which you just
    extracted the files) to wherever you would like to be its
    permanent location.  Then, open a Command Prompt window,
    navigate to that location, and run `ruby dk.rb init`.  (I
    put the DevKit in "C:\RubyDevKit" so that it would be
    right next to the Ruby installation, in "C:\Ruby22-x64.")
    Finally, run `ruby dk.rb install`.
    
    <pre>
    <span class="muted">C:\Users\User Name></span>cd ..\..
    <span class="muted">C:\></span>cd RubyDevKit
    <span class="muted">C:\RubyDevKit></span>ruby dk.rb init
    <span class="muted">[INFO] found RubyInstaller v2.2.5 at C:/Ruby22-x64
    Initialization complete! Please review and modify the auto-
    generated 'config.yml' file to ensure it contains the root
    directories to all of the installed Rubies you want enhanced by
    the DevKit.</span>
    <span class="muted">C:\RubyDevKit></span>ruby dk.rb install
    <span class="muted">[INFO] Installing 'C:/Ruby22-x64/lib/ruby/site_ruby/2.2.0/rubygems/defaults/operating_system.rb'
    [INFO] Installing 'C:/Ruby22-x64/lib/ruby/site_ruby/devkit.rb'</span>
    </pre>

4.  Install [Bundler](http://bundler.io/) (using
    [Ruby](https://www.ruby-lang.org/)'s `gem install` command):

    <pre>
    <span class="muted">C:\Users\User Name\ccsc></span>gem install bundler
    </pre>
    
    The first time you run this command, you'll get a Windows
    Security Alert message---"Windows Firewall has blocked some
    features of this program..."  Click "Allow access" to continue.

    Unfortunately you may also get a certificate verification error
    when you try to run `gem install`.  If you do, you'll need to
    manually update the "rubygems" package in order to get an
    updated SSL certificate.  You can get the update from
    [https://rubygems.org/gems/rubygems-update/versions/2.6.7](https://rubygems.org/gems/rubygems-update/versions/2.6.7/) (Click "Download," on
    the right side near the bottom of the page.)  To install
    the update:
    
    <pre>
    <span class="muted">C:\Users\User Name\Downloads></span>gem install --local rubygems-update-2.6.7.gem
    <span class="muted">Successfully installed rubygems-update-2.6.7
    Parsing documentation for rubygems-update-2.6.7
    Installing ri documentation for rubygems-update-2.6.7
    Done installing documenation for rubygems-update after 40 seconds
    1 gem installed
    C:\Users\User Name\Downloads></span>update_rubygems
    <span class="muted">RubyGems 2.6.7 installed
    Parsing documentation for rubygems-2.6.7
    Installing ri documenation for rubygems-2.6.7...</span>
    </pre>
    
    At this point you should have the updated SSL certificate,
    and `gem install bundler` should work if you try it again.

5.  Navigate to the repository folder; use Bundler to update Ruby
    packages (based on contents of repository's "Gemfile") needed
    for local [Jekyll](https://jekyllrb.com) installation:

    <pre>
    <span class="muted">C:\Users\User Name\ccsc\ccsc-example></span>bundle update
    <span class="muted">Fetching gem metadata from https://rubygems.org/..........
    Fetching version metadata from https://rubygems.org/.
    Resolving dependencies...</span>
    </pre>

6.  Execute Jekyll's `serve` command via Bundler's `exec` command:

    <pre>
    <span class="muted">C:\Users\User Name\ccsc\ccsc-example></span>bundle exec jekyll serve
    <span class="muted">Configuration file: C:/Users/User Name/ccsc/ccsc-example/_config.yml
                Source: C:/Users/User Name/ccsc/ccsc-example
           Destination: C:/Users/User Name/ccsc/ccsc-example/_site
     Incremental build: disabled. Enable with --incremental
          Generating...
                        done in 0.312 seconds.
     Auto-regeneration: enabled for 'C:/Users/User Name/ccsc-tutorial/ccsc-example'
    Configuration file: C:/Users/User Name/ccsc-tutorial/ccsc-example/_config.yml
        Server address: http://127.0.0.1:4000/ccsc-example/
      Server running... press ctrl-c to stop.</span>
    </pre>
    
    Open a web browser and go to the URL Jekyll gives you
    (`http://127.0.0.1:4000/ccsc-example/`, after "Server address" in the
    example above).  If everything's worked correctly, you should see a page
    titled "CCSC Example" with a few titles, a list, a little bit of source
    code and a little bit of mathematical notation.

## OS X

1.  Open a Terminal window and run the following command:

    <pre>
    <span class="muted">Users Mac:~ user$</span> git config --global user.name "YOUR NAME"
    </pre>

    Unless you already have the OS X Command Line Developer Tools installed,
    you'll see a popup asking you whether you'd like to install them.  Choose
    "Install." (Don't choose "Get Xcode" unless you want the full Xcode
    environment---which is much more than you need for this tutorial.)

    When the installation finishes, try the `git` command again.  (It should
    work now.)

    <pre>
    <span class="muted">Users-Mac:~ user$</span> git config --global user.name "YOUR NAME"
    </pre>

2.  Finish setting up [Git](https://git-scm.com), and then make a local copy of the example
    repository I created for this tutorial.  (I created a folder called
    "ccsc" and put the repository copy in that folder.)

    <pre>
    <span class="muted">Users-Mac:~ user$</span> git config --global user.email "YOUR EMAIL ADDRESS"
    <span class="muted">Users-Mac:~ user$</span> mkdir ccsc
    <span class="muted">Users-Mac:~ user$</span> cd ccsc
    <span class="muted">Users-Mac:ccsc user$</span> git clone https://github.com/dvon/ccsc-example
    <span class="muted">Cloning into 'ccsc-example'...
    remote: Counting objects: 55, done.
    remote: Compressing objects: 100% (3/3), done.
    remote: Total 55 (delta 0), reused 0 (delta 0), pack-reused 52
    Unpacking objects: 100% (55/55), done.
    Checking connectivity... done.</span>
    </pre>

3.  Install [Bundler](http://bundler.io/) (using
    [Ruby](https://www.ruby-lang.org/)'s `gem install` command):

    <pre>
    <span class="muted">Users-Mac:ccsc user$</span> sudo gem install bundler
    <span class="muted">Password:
    Fetching: bundler-1.13.6.gem (100%)
    Successfully installed bundler-1.13.6
    Parsing documentation for bundler-1.13.6
    Installing ri documentation for bundler-1.13.6
    1 gem installed</span>
    </pre>

    *Note:  If you have OS X Yosemite or Sierra you should have Ruby version
    2.0.0 installed by default.  You need Ruby version 2.x.x for this tutorial, so if
    you have an earlier version of OS X you may need to update Ruby.*

4.  Navigate to the repository folder; use Bundler to update Ruby
    packages (based on contents of repository's "Gemfile") needed
    for local [Jekyll](https://jekyllrb.com) installation.
    (If you get a message about Rubygems not being threadsafe, it's safe to ignore
    it.)

    <pre>
    <span class="muted">Users-Mac:ccsc user$</span> cd ccsc-example
    <span class="muted">Users-Mac:ccsc-example user$</span> sudo bundle update
    <span class="muted">Password:
    Fetching gem metadata from https://rubygems.org/...........
    Fetching version metadata from https://rubygems.org/..
    Fetching dependency metadata from https://rubygems.org/.
    Resolving dependencies...</span>
    </pre>
    

5.  Execute Jekyll's `serve` command via Bundler's `exec` command:

    <pre>
    <span class="muted">Users-Mac:ccsc-example user$</span> bundle exec jekyll serve
    <span class="muted">Configuration file: /Users/user/ccsc/ccsc-example/_config.yml
                Source: /Users/user/ccsc/ccsc-example
           Destination: /Users/user/ccsc/ccsc-example/_site
     Incremental build: disabled. Enable with --incremental
          Generating... 
                        done in 0.229 seconds.
     Auto-regeneration: enabled for '/Users/user/ccsc/ccsc-example'
    Configuration file: /Users/user/ccsc/ccsc-example/_config.yml
        Server address: http://127.0.0.1:4000/ccsc-example/
      Server running... press ctrl-c to stop.</span>
    </pre>

    Open a web browser and go to the URL Jekyll gives you
    (`http://127.0.0.1:4000/ccsc-example/`, after "Server address" in the
    example above.)  If everything's worked correctly, you should see a page
    titled "CCSC Example" with a few titles, a list, a little bit of source
    code and a little bit of mathematical notation.

[^cloud9]: Cloud 9 recently (as of fall 2016) changed their registration
           process so that a credit card is required, even if you only use
           the free basic service.  With that in mind, if you'd prefer not
           to use Cloud 9, the Linux instructions above should also work
           on [Nitrous](https://www.nitrous.io), on a local Linux (i.e.,
           recent Ubuntu) installation, or a virtual Linux installation
           (on, e.g., [VirtualBox](https://www.virtualbox.org)).
