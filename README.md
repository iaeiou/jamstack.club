# Jamstack.club?

The [Jamstack.club](https://jamstack.club) is a collection of free Jamstack Themes for Hugo, Eleventy, Jekyll, Gatsby and [many other static-sites generators](https://jamstack.club/ssg).  
Filter, sort, preview, and find the best Jamstack Theme for your next project!

Now live at https://jamstack.club !


## Contribute

Willing to help? Welcome aboard!

**There are many ways you can contribute to the Jamstack.club**

**Note: We value each contribution** and, if you like to, we can acknowledge you using the [@allcontributors](https://github.com/all-contributors/all-contributors#readme) principles.

### Report a problem

**Found an issue?** You can [submit a bug report](https://github.com/RoneoOrg/jamstack.club/issues), or [drop us an email](https://jamstack.club/contact/).

We'll get back to you as soon as possible.
### Submit A Theme

A theme must meet only two requirements to be submitted:

* The source code must be open-source and public
* The demo URL links must point to a demo of the theme and not your personal or business site.

Allright? Let's go!

1. Fork this repo and create a new markdown `.md` file in `content/theme` folder. For example `hugo-air.md`. 
2. Add the required front-matter as shown in the **Example Theme** below.
3. Submit a pull request

> **Tip:** Do not generate the Github stars or theme screenshots. Please just submit the markdown file in your pull request.

**Example Theme**
```yaml
---
title: "My Theme Name"
github: https://github.com/username/repo
demo: https://www.demo.com # Please make sure this links to a theme demo and not your personal/business site. The demo url must use https
author: authorname
date: 2019-08-20 # Enter the date you submitted the theme YYYY-MM-DD
ssg:
  - Gridsome # at least 1 ssg is required
cms:
  - No CMS # at least 1 cms is required. If your theme uses markdown (no CMS) the cms should be "No CMS"
css: # css is optional
  - Bootstrap 
archetype: # archetype is optional
  - Blog
  - Portfolio
description: This is an amazing theme and this is a small description about it!
---

# A simple starter kit for Gridsome

This theme is a lightweight starter kit. It also gives you a well organised starting point to extend it for yourself.

## Features

* Customisable design tokens to make it your own  
* Customisable global data and navigation  
* Tags and tag archives  
* Progressively enhanced, semantic and accessible  
```

## How does it work?

Each theme is described in a Markdown file. (See [this example](https://raw.githubusercontent.com/RoneoOrg/jamstack.club/main/content/theme/hugo-restaurant.md) to get an idea).

The website is then automatically build with [Hugo](https://gohugo.io) and [a few JS scripts](https://github.com/RoneoOrg/jamstack.club/tree/main/scripts) automates the creation of the Github stats and generate a screenshot.  
A dedicated page is created for each theme, along with a Demo. See [the page for the theme "Restaurant"](https://jamstack.club/theme/hugo-restaurant/) for example.

The index is updated, still automatically, and the website is published, hosted by [Netlify](https://www.netlify.com/).


## Develop Locally

Github stars, image thumbnails and last commit date are generated at build time when this site is deployed to Netlify. Basically the Netlify site runs `npm run deploy`

This site is built on [Hugo](https://gohugo.io/)

Development Server

```
hugo serve
```

Build Site

```
hugo
```

Generate Github stars, image screenshots etc

```
npm install
export GITHUB_TOKEN=XXX
npm run deploy
```

> Generating github data requires a Github Token. You can generate this token in your Github account at settings > developer settings > personal access tokens https://github.com/settings/tokens

## Submitting New Categories
Themes can be categorised with terms from these 4 taxonomies. `ssg`, `cms`, `css` and `archetype`

If you are adding a theme which uses an SSG or CMS which doesnt exist you will need to add it as part of your pull-request.

1. Create a new taxonomy term by creating the markdown file under `content/ssg/` or `content/cms`. For example let's say you wanted to add a new SSG called "Super Duper". Add a file under `content/ssg/super-duper/_index.md` and add the following frontmatter
```
---
title: "Super Duper"
icon: images/icons/super-duper.svg 
official_url: https://super-duper.org
---
```

2. Add the icon. You will need to upload an icon into `static/images/icons`. The icon should in SVG format under 3KB. If it's a PNG please make sure the size is 60x60px and the size is as small as possible (you should be able to keep it under 5KB)
3. Update the Javascript filter logic. Update the file `themes/jamstackthemes/assets/js/filter/filter-groups.js` and add `super-duper` to the ssg array.