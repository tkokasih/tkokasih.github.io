# jekyll

## Background

I'm using Github pages which uses Jekyll as default.
This is a quickstart on how Jekyll works.

## Pages, Posts, Drafts

* Pages

  All files that will be transformed to html page.
  Example includes this page.
  Typical pages includes:
  * 

* Posts

  File lives in `_posts/` directory with some convention that will be transformed into blog posts.
  Convention:
  * filename: `YEAR-MONTH-DAY-title.MARKUP`, e.g. `2022-01-01-some-title-here.md`
  * content: begin with frontmatter, e.g.
    ```
    ---
    layout: post
    title: "This thing between two triple dash is front matter"
    tags: jekyll tech notes 
    ---

    # Heading 1

    Some content here
    ```

* Drafts

  Same like post, but not ready to be published.
  It lives under `_drafts/` folder.


## Layouts

Layout lives under `_layouts/` folder and will be used to layout the pages above. Example:

```
---
layout: default
---
<head>
  <title>{{ page.title }}</title>
</head>
<body>
  {{ content }}
</body>
<footer>
  This is footer
</footer>
```

* special naming:
  * `home.html`: for home page
  * `page.html`: for pages
  * `post.html`: for posts

* Layout can inherit from other layout by specifying it in the frontmatter:
  ```
  ---
  layout: parentLayout
  ---

  child-specific layout here
  ```

## Draft Points

* Assets
* 