---
layout: post
title: Github Flavored Markdown
---

{{ page.title }}
================

<p class="meta">28. November 2014 - Wartenberg</p>


##  config

before you can use the update github-flavored-markdown
you must update *_config.yml* with:

```yaml
markdown: redcarpet
redcarpet:
  extensions: ["no_intra_emphasis",
               "fenced_code_blocks",
               "autolink",
               "tables",
               "highlight",
               "with_toc_data",
               "strikethrough"]
```

# Syntax

## auto link

http://example.com

## highlighted
```
This is ==highlighted==
```
This is ==highlighted==

## Syntax highlighted

ruby

```ruby
require 'redcarpet'
markdown = Redcarpet.new("Hello World!")
puts markdown.to_html
```

sql

```sql
SELECT * FROM mytable WHERE 1=2;
```

## Strikethrough

```
this is ~~good~~ bad
```
this is ~~good~~ bad

## more

```
**Everyone _must_ attend the meeting at 5 o'clock today.**
```
**Everyone _must_ attend the meeting at 5 o'clock today.**

[more info about GitHub Markdown](https://help.github.com/articles/github-flavored-markdown)

[Markdown](https://help.github.com/articles/markdown-basics/)

