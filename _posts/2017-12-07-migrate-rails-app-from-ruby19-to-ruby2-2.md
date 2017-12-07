---
layout: post
title: Migrate a Rails Application from ruby 1.9.3 to ruby 2.2
---

{{ page.title }}
================

As first step to migrate all rails 3 application to rails 5.1 we moved
from ruby 1.9.3 to ruby 2.2.

## Problems

1. YAML serializer was moved from Syck to Psych. There a some issues with utf-8 encoding

2. ```iconv``` must be added to the Gemfile

3. ```test-unit```  must be added to the Gemfile

4. with ruby2.2 you gets warnings when you have duplicate keys in a Hash

## Improvments

* the Application uses only have of the memory that leads to imporvment of the overall performance