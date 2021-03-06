# rimdev.io

A new RIMdev jekyll experience. Minimal, focused on reading content.

Photography by JJ Walck

## Setup

1. [Install Jekyll](http://jekyllrb.com)
2. Fork the [RIMdev blog](https://github.com/ritterim/rimdev-blog/fork)
3. Clone the repo you just forked.
4. Run `run.cmd` or `run.sh`.

## Tests

Tests are ran with `npm test`. This runs [markdown-proofing](https://www.npmjs.com/package/markdown-proofing) on all posts. See the `scripts` in `package.json` for more runnable commands.

## New in this release

- Jekyll 3 ([faster](https://github.com/blog/2100-github-pages-now-faster-and-simpler-with-jekyll-3-0), [release notes](https://jekyllrb.com/news/2015/10/26/jekyll-3-0-released/))
- [Bootstrap 4 (Alpha 4)](http://v4-alpha.getbootstrap.com/getting-started/introduction/)
- [Jekyll @mentions](https://github.com/jekyll/jekyll-mentions)
- [Jekyll gist](https://github.com/jekyll/jekyll-gist) support
- author pages (see below)

## Creating posts

You can use the `initpost.sh` to create your new posts. Just follow the command:

```
./initpost.sh -c Post Title
```

The new file will be created at `_posts` with this format `date-title.md`.

When you're done, run `npm run check` to check it over.

### Adding an image

Adding an image is easy enough, remember to add the Bootstrap 4 responsive image class `.img-fluid`. If you want to add a light border, use `{: .img-fluid .border}`

```
[ Your image description, i.e., alt tag content ]( /path/to/image.jpg ){: .img-fluid }
```

## Front-matter

### Posts

When you create a new post, you need to fill the post information in the front-matter, follow this example:

```
---
layout: post
title: "How to use"
authors: <Your name here>
date: 2015-08-03 03:32:44
image: "/images/my-great-image.jpg"
image_url: <url/page associated with image>
image_credit: <name for image credit>
tags:
- jekyll
- template
categories:
- I love Jekyll
twitter_text: "How to install and use this template"
---
```
If the page has no image, `image:` can be omitted entirely. A default system image will be used. If `image_credit:` is specified, then `image_url:` should also be specified.

> TAGS: Check existing Tags [here](http://rimdev.io/tags/) before creating new ones

**The difference between single and multiple authors:**

```
# single author
authors: <author name>

# multiple authors
authors:
- <First author>
- <Second author>
```
### CC Attribution blog images

Using a Creative Commons image requiring attribution?

```
image: https://farm5.staticflickr.com/4103/5029857600_d8ed3aaa06_b_d.jpg
image_url: https://www.flickr.com/photos/khawkins04/
image_credit: Ken Hawkins
```

### Author pages

```
---
layout: author
author: Bill Boga
permalink: /bill-boga/
image: /images/default/annex-billboga.jpg
avatar: false
---
```
The last 2 items are optional; If the page has no image, `image:` can be omitted entirely. A default system image will be used. You only need to include `avatar: false` if omitting your avatar.

## Running the blog locally

Create a local config file `_config.local.yml` with the single entry `url: http://localhost:4000` (unless you're running a different port via `--port <port number>`)

```
jekyll s --config _config.yml,_config.local.yml
```
