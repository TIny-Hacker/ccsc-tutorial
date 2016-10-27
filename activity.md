---
title: Activity
section: 3
layout: default
summary:
    "Try creating your own GitHub Pages site."
---

# Activity

Now that you've seen the key pieces of an example site, let's create
a new site from scratch.

## Create the Site Repository on GitHub

1.  Go to [GitHub](https://github.com), sign in to your account.  (Create
    an account if you don't have one---a free personal account is fine.)
    Click the plus sign in the upper right corner, pick "New repository."

2.  Under "Repository name," enter a name; check "Initialize this
    repository with a README"; click "Create repository."  This should
    take you to a new page, created for your new repository.

3.  Select the "Settings" tab near the top and towards the right side
    of the page.  Scroll down to "GitHub Pages."  Under "Source," click
    "None" and change it to "master branch."  Then click "Save."

4.  Go back to the "<> Code" tab and select "Create new file."  Enter
    the name "index.md" at the top, enter the text you see below
    in the editor section, and then click "Commit new file" at the bottom.

    ```markdown
    ---
    layout: default
    ---

    # Hello, World!
    ```

5.  Open a new browser tab and go to `https://username.github.io/reponame/`,
    where `username` is your GitHub username and `reponame` is the name
    of your new repository.

## Create & Test Local Copy, Update GitHub Copy

*Note: For these instructions I'll assuming you're working in Linux, on
a Cloud 9 virtual machine, with GitHub username `username` and repository
name `reponame`.*

1.  Create a local copy of your new respository; navigate to the repository
    folder:

    <pre>
    <span class="muted">username:~/workspace $</span> git clone https://github.com/username/reponame
    <span class="muted">Cloning into 'reponame'...
    remote: Counting objects: 15, done.
    remote: Compressing objects: 100% (9/9), done.
    remote: Total 15 (delta 0), reused 0 (delta 0), pack-reused 0
    Unpacking objects: 100% (15/15), done.
    Checking connectivity... done.
    username:~/workspace $</span> cd reponame
    <span class="muted">username:~/workspace/reponame (master) $</span>
    </pre>

2.  Create `Gemfile` with the text below; save it in the repository
    folder.  (You don't need the last line if you don't plan to make a
    local copy on Windows in the future.)

    ```ruby
    source 'https://rubygems.org'
    gem 'github-pages', group: :jekyll_plugins
    gem 'wdm', '>= 0.1.0' if Gem.win_platform?
    ```

3.  Run Bundler's `install` command to update Ruby packages.  (Don't really
    need to do this, if you followed the instructions on the setup page
    and already did, but if you were starting from scratch this would be
    the next step.)

    <pre>
    <span class="muted">username:~/workspace/reponame (master) $</span> bundle install
    <span class="muted">Fetching gem metadata from https://rubygems.org/...........
    Fetching version metadata from https://rubygems.org/..
    Fetching dependency metadata from https://rubygems.org/.
    Resolving dependencies...</span>
    </pre>

4.  Create `_config.yml` with `baseurl` set; save it in the repository
    folder.

    <pre>
    <span class="muted">username:~/workspace/reponame (master) $</span> echo "baseurl: /reponame" > _config.yml
    </pre>

5.  Run Jekyll's `serve` command via `Bundler`:

    <pre>
    <span class="muted">username:~/workspace/reponame (master) $</span> bundle exec jekyll serve -H 0.0.0.0 -P 8080
    <span class="muted">Configuration file: /home/ubuntu/workspace/reponame/_config.yml
                Source: /home/ubuntu/workspace/reponame
           Destination: /home/ubuntu/workspace/reponame/_site
     Incremental build: disabled. Enable with --incremental
          Generating...
         Build Warning: Layout 'default' requested in index.md does not exist.
                        done in 0.077 seconds.
     Auto-regeneration: enabled for '/home/ubuntu/workspace/reponame'
    Configuration file: /home/ubuntu/workspace/reponame/_config.yml
        Server address: http://0.0.0.0:8080/reponame/
      Server running... press ctrl-c to stop.</span>
    </pre>

    You should see a popup from Cloud 9 with a link; click the link.  In
    the tab that opens, add `/reponame/` to the URL and refresh the page.
    You should see the "Hello, World!" page you created.

6.  Add your new files to the repository.

    I've made the example here a little longer than it needs to be in
    order to show you some useful `git` commands.  The commands here...

    -   Add everything in the folder to the repo.
    -   Remove the folder `_site` from the repo, without deleting it
        locally.
    -   Remove `Gemfile.lock` from the repo, without deleting it locally.
    -   Check what's currently marked as part of the repo.

    <pre>
    <span class="muted">username:~/workspace/reponame (master) $</span> git add .
    <span class="muted">username:~/workspace/reponame (master) $</span> git add .
    <span class="muted">username:~/workspace/reponame (master) $</span> git reset _site
    <span class="muted">username:~/workspace/reponame (master) $</span> git reset Gemfile.lock
    <span class="muted">username:~/workspace/reponame (master) $</span> git status
    <span class="muted">On branch master
    Your branch is up-to-date with 'origin/master'.
    Changes to be committed:
      (use "git reset HEAD &lt;file&gt;..." to unstage)

            new file:   Gemfile
            new file:   _config.yml

    Untracked files:
      (use "git add &lt;file&gt;..." to include in what will be committed)

            Gemfile.lock
            _site/</span>
    </pre>

7.  Commit changes (with a descriptive message); push changes to
    GitHub copy of the repository.

    <pre>
    <span class="muted">username:~/workspace/reponame (master) $</span> git commit -a -m "Added Gemfile and _config.yml."
    <span class="muted">[master e3e5ce9] Added Gemfile and _config.yml
     2 files changed, 4 insertions(+)
     create mode 100644 Gemfile
     create mode 100644 _config.yml
    username:~/workspace/reponame (master) $</span> git push
    <span class="muted">Username for 'https://github.com':</span> username
    <span class="muted">Password for 'https://username@github.com':
    Counting objects: 4, done.
    Delta compression using up to 8 threads.
    Compressing objects: 100% (3/3), done.
    Writing objects: 100% (4/4), 490 bytes | 0 bytes/s, done.
    Total 4 (delta 0), reused 0 (delta 0)
    To https://github.com/username/reponame
       29ebfac..e3e5ce9  master -> master</span>
    </pre>

## Make Your Site More Interesting...

Here are some more complicated examples to look at as you build your
site from "Hello, World!" to something more interesting.

*Note: If you leave Jekyll's server running, as you make changes to your
site's files, the HTML output will be automatically updated, giving you
a live view of your changes.*

### This tutorial site: [https://github.com/dvon/ccsc-tutorial](https://github.com/dvon/ccsc-tutorial)

-   `index.md`, together with more complicated front matter at the
    beginning of `setup.md`, `example.md`, etc., shows how to set things
    up so that the index page is updated automatically by Jekyll (Liquid?)
    as you add new pages to a multi-page site.

-   `setup.md` shows how HTML can be included in a Markdown
    file---you just put it in :)

-   `setup.md` shows how you can include a link to a title later in the
    page, or to a footnote at the end.

-   {% raw %}`example.md` shows how you can exclude a section of a
    Markdown file from Liquid processing, in case you want a literal
    Liquid object, for example `{{ content }}`, in your page.{% endraw %}

### The Graphics Course website for which I first started using GitHub Pages:  [https://github.com/dvon/cgbk](https://github.com/dvon/cgbk)

-   `_layouts/default.html`, together with `index.md` and the various
    lesson pages, shows how HTML code from a template can be
    selectively included in pages based on the template.

-   `lessons/Transformations (Part 2).md` shows more complex mathematical
    notation, included within a paragraph and as an independent
    centered block.

-   `index.md` shows how you can include Markdown
    within HTML within a Markdown file (where lesson summaries are
    generated within the Liquid loop---this was needed for lesson 6's
    summary).

-   `_layouts/default.html`, together with the various lessons pages,
    shows how, with some determination, you can get automatically numbered
    exercises (or examples, etc.) within a page.