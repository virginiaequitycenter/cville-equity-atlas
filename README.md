# Charlottesville Regional Equity Atals

This is the repository for the [Charlottesville Regional Equity Atlas](https://virginiaequitycenter.github.io/cville-equity-atlas/) site, and documentation related to updating the site.

There's a [homepage for all Atlas-related documentation here](), as well as some useful info below.

**Want help?** Please feel free to reach out to Beth with any questions - there is a lot to learn here, and can be hard to quickly find answers!

## Table of Contents

1. [Site basics](#site-basics)
2. [Contribute to the site](#contribute-to-the-site)
3. [Add an issue](#get-help-or-add-an-issue)
4. [Working with the site locally](#working-with-the-site-locally)
	* [Prerequisites](#prerequisites)
	* [Installation](#installation)
	* [Building the site](#building-the-site)

## Site Basics

[Equityatlas.virginiaequitycenter.org](https://virginiaequitycenter.github.io/cville-equity-atlas/)
  * Our "live" website that the world can see.
  * The site is published using Github pages (more on that below), but also has a redirect from [equityatlas.virginiaequitycenter.org](equityatlas.virginiaequitycenter.org)
  * Currently, updating the code in the "main" branch of this repo will not update the live site. The site is currently deployed from the gh-pages branch - more on that [here]().

## Working with Jekyll

[Jekyll static site builder](https://jekyllrb.com/)
  * We use [Jekyll](https://jekyllrb.com) for publishing our site.
  * Jekyll takes markdown and html files and uses layouts to create a static website. They provide ample [documentation on the basics](https://jekyllrb.com/docs/), and there is also a large community of users, so searching for help on stackoverflow and the like often provides a lot of solutions.
  * [Learn how to work with the site locally]() and [publish updates]().
  * Get to know the Jekyll directory structure for the Equity Atlas site [here]().
  * Understand front matter in Jekyll and how to make new pages [here]().

## Using R Markdown documents

   * The Equity Atlas publishes reports initally created using R Markdown documents with a number of commonly used R packages.  
   * There is a specific workflow and considerations for creating a report page on the Atlas site, see the steps documented [here]().

## Embed R Shiny apps

   * The Equity Atlas also embeds R shiny applications, using the `<iframe>` tag. See an [example page](https://github.com/virginiaequitycenter/cville-equity-atlas/blob/main/pages/cville-equity-dashboard.html), and further documentation [here]().

## Making other site updates

