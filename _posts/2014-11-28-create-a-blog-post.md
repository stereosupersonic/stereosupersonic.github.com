---
layout: post
title: Create a blog post
---

{{ page.title }}
================

<p class="meta">28. November 2014 - Wartenberg</p>


* create a new file under _posts format: YYYY-MM-DD-title.md
* add a header like

<pre class="terminal"><code>
---
layout: post
title: My Title
---

{{ page.title }}
================
</code></pre>

* add content with markdown
* start preview server bundle exec jekyll serve --watch
* open http://0.0.0.0:4000/
* deploy

<pre class="terminal"><code>
git commit "my new blog post"
git push origin master"
</code></pre>

[Mastering Markdown](https://guides.github.com/features/mastering-markdown/)

[Markdown Help](https://help.github.com/articles/markdown-basics)

[GitHub Markdown](https://help.github.com/articles/github-flavored-markdown)

[Writing on GitHub](https://help.github.com/articles/writing-on-github)


