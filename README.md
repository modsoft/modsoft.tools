# modsoft.tools

Tech notes, published with Jekyll on GitHub Pages.

## Add a post

Create `_posts/YYYY-MM-DD-title.md`:

```markdown
---
layout: post
title: Title of the note
---

Write in markdown.
```

Push to `main`. GitHub Pages publishes the post.

## Local preview

Requires Ruby.

```
bundle install
bundle exec jekyll serve
```
