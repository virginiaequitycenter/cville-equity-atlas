# Charlottesville Regional Equity Atlas Documentation

## Table of Contents

1. [Site basics](#site-basics)
2. [Working with Jekyll](#working-with-jekyll)
3. [Site structure](#site-structure)
4. [Working with the site locally](#working-with-the-site-locally)
5. [Writing and editing site content](#writing-and-editing-site-content)
   - [Using R Markdown documents](#using-r-markdown-documents)
   - [Embed R Shiny apps](#embed-r-shiny-apps)
8. [Publishing updates](#publishing-updates)

## Site Basics

[equityatlas.virginiaequitycenter.org](https://virginiaequitycenter.github.io/cville-equity-atlas/)
  * Our "live" website that the world can see.
  * The site is published using Github pages, but also has a redirect from [equityatlas.virginiaequitycenter.org](equityatlas.virginiaequitycenter.org)
  * Currently, updating the code in the "main" branch of this repo will not update the live site. The site is currently deployed from the gh-pages branch - more on that in [Publishing Updates](#publishing-updates).

## Working with Jekyll

  * We use [Jekyll](https://jekyllrb.com) for publishing our site.
  * Jekyll takes markdown and html files and uses layouts to create a static website. They provide ample [documentation on the basics](https://jekyllrb.com/docs/), and there is also a large community of users, so searching for help on stackoverflow and the like often provides a lot of solutions.

## Site Structure

The Equity Atlas site follows the directory structure of a [Jekyll site](https://jekyllrb.com/docs/structure/). The repository is organized like this:

**[/_data](https://github.com/virginiaequitycenter/cville-equity-atlas/tree/main/_data):** This folder contains data files needed to run the site. Currently it includes [navbar.yml](https://github.com/virginiaequitycenter/cville-equity-atlas/blob/main/_data/navbar.yml) that provides the data for the site's primary navigation.

**[/_includes](https://github.com/virginiaequitycenter/cville-equity-atlas/tree/main/_includes):** This folder contains partial html files that are re-used throughout the site. This includes the content for site basics like the head metadata, header, footer, and navbar, as well as partials specific to implementing html/js for R packages used in reports. This includes leaflet, plotly, reactable, tabsets, and floating TOC. 

**[/_layouts](https://github.com/virginiaequitycenter/cville-equity-atlas/tree/main/_layouts):** This folder includes page templates for the site. Currently included are:
  * [default.html](https://github.com/virginiaequitycenter/cville-equity-atlas/blob/main/_layouts/default.html): This is the default page template, and is currently used for the home page (index.html) as well as pages with embedded R Shiny apps.
  * [landing-page.html](https://github.com/virginiaequitycenter/cville-equity-atlas/blob/main/_layouts/landing-page.html): This template is used for site landing pages - Dashboards, Reports, Resources, and About
  * [report.html](https://github.com/virginiaequitycenter/cville-equity-atlas/blob/main/_layouts/report.html): This is the template for Atlas reports generated from an R Markdown file.

**[/assets](https://github.com/virginiaequitycenter/cville-equity-atlas/tree/main/assets)**
  * [/css](https://github.com/virginiaequitycenter/cville-equity-atlas/tree/main/assets/css): The styling for the site. SASS is used, see me for needed updates
  * [/img](https://github.com/virginiaequitycenter/cville-equity-atlas/tree/main/assets/img): All image files for the site
  * [/js](https://github.com/virginiaequitycenter/cville-equity-atlas/tree/main/assets/js): Javascript files for RMD produced reports

**[/docs](https://github.com/virginiaequitycenter/cville-equity-atlas/tree/main/docs):** This folder includes the documentation for the site, as well as the needed template file for the workflow from R to Jekyll ([atlas-rmd-template.html](https://github.com/virginiaequitycenter/cville-equity-atlas/blob/main/docs/atlas-rmd-template.html))

**[/pages](https://github.com/virginiaequitycenter/cville-equity-atlas/tree/main/pages):** This folder holds the site's content, organized as follows:
  * [/dashboards](https://github.com/virginiaequitycenter/cville-equity-atlas/tree/main/pages/dashboards)
    * climate-dashboard.html (Cville Climate Equity Atlas, embedded R Shiny app)
    * cville-equity-dashboard.html (Cville Regional Equity Atlas, embedded R Shiny app)
    * index.html (Dashboards landing page)
  * [/reports](https://github.com/virginiaequitycenter/cville-equity-atlas/tree/main/pages/reports) - below pages are reports produced from R Markdown files
    * albemarle-profile.html
    * index.html (Reports landing page)
    * orange-dot.html
    * school-composition.html
    * stepping-stones.html
    * stepping-stones-supplement.html
  * about.html (About landing page)
  * resources.html (Resources landing page)

**[_config.yml](https://github.com/virginiaequitycenter/cville-equity-atlas/blob/main/_config.yml):** The site's configuration settings. See [Jekyll documentation](https://jekyllrb.com/docs/configuration/).

**[index.html](https://github.com/virginiaequitycenter/cville-equity-atlas/blob/main/index.html):** This is the site's homepage

## Working with the site locally

If needed, review documentation on [working with the Github repo and command line](https://github.com/virginiaequitycenter/cville-equity-atlas/blob/main/docs/command-line.md) before installing Jekyll and working with the site locally.

1. Install Jekyll and check other prerequisites following their documentation: [Jekyll Quickstart Guide](https://jekyllrb.com/docs/). Please see me if you'd like assistence with this step.

2. Clone this Git repository:

```bash
git clone https://github.com/virginiaequitycenter/cville-equity-atlas.git
```

3. Change directory into the project folder:

```bash
cd cville-equity-atlas
```

4. To install all the necessary gems specified in the `Gemfile.lock`, run Bundler:

```bash
bundle install
```

5. To build and serve the site locally, run:

```bash
bundle exec jekyll serve
```

The site should build and be accessible at [http://localhost:4000](http://localhost:4000).

To stop the local server, press `ctrl c` into your terminal.

## Writing and editing site content

See more details on how to write and edit page content, front matter, and page layouts:

[Writing and editing pages]()

### Using R Markdown documents

The Equity Atlas publishes reports initally created using R Markdown documents with a number of commonly used R packages.  

   * There is a specific workflow and considerations for creating a report page on the Atlas site, see the steps documented [here]().

### Embed R Shiny apps

The Equity Atlas also embeds R shiny applications, using the `<iframe>` tag. See an [example page](https://github.com/virginiaequitycenter/cville-equity-atlas/blob/main/pages/dashboards/cville-equity-dashboard.html).

   * To create a new page with embedded content, copy the above html file and update the front matter and `<iframe>` src URL.

## Publishing updates

The live Atlas site is currently deployed from the `gh-branch` of this repository. The first time you publish updates, you will need to clone this repo's `gh-pages` branch into the `_site` directory. You will only need to do this step once, in future deploys skip to step 3.

1. Remove all content from the `_site` directory:

```bash
rm -r _site/*
```

2. Clone the repo's `gh-pages` branch into the `_site` directory:

```bash
git clone -b gh-pages `git config remote.origin.url` _site
```

*Start here for future updates*

3. Rebuild the contents of the `_site` directory:

```bash
bundle exec jekyll build
```
4. Change directory into `_site`:

```bash
cd _site
```

5. Add all files for commit:

```bash
git add -A
```

6. Commit with comment:

```bash
git commit -m "site updates"
```

7. Push to remote:

```bash
git push
```

Your updates should now be deploying on Github, check the Actions tab to see the progress of this workflow. The updates will be on the live site after this workflow completes. 

**NOTE:** This process only updates the files in the deployment branch, `gh-pages`. When you have completed these steps, be sure the return to the main `cville-equity-atlas` directory and push changes to the main branch as well. 