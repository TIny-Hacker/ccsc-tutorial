---
title: Example
section: 2
layout: default
summary:
    "Look carefully at key source files for the ccsc-example site."
---

# Example

Let's look at the key source files from which the ccsc-example
site is generated.

## index.md

This is the file from which index.html is generated.  "md" stands for
[Markdown](https://daringfireball.net/projects/markdown/), a simple
plaintext format designed to be easy to write and easy to read (much
easier to write and read than HTML source files, for example).  The
original Markdown software tool generates HTML from Markdown source
files; several alternative tools exist for generating HTML, PDF, or
other output formats.  Among them is
[kramdown](http://kramdown.gettalong.org/), which is the default
Markdown tool for [Jekyll](https://jekyllrb.com/), the static website
generator used by GitHub Pages.

So let's take a look at basic Markdown syntax, as illustrated by
index.md:

~~~markdown
# CCSC Example

A (very short) paragraph,
followed by a list:

-   An item
-   An italicized *item*

-   A third
    item.
~~~

A line beginning with `#` is a title.  A block of text is a
paragraph, continuing up until the next blank line---linebreaks within
the block will be ignored in the generated HTML; the text will be
broken up into lines by the browser based on the width of the window.

A line beginning with a minus sign, continuing with text four spaces
from the left, is an item in a list.  List items may be separated by
a blank line; the list ends with two blank lines or something that
isn't a list item, e.g., another title...

- test
- test


- test