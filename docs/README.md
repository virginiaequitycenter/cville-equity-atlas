# Charlottesville Regional Equity Atlas Documentation

## Table of Contents

1. [Github and Command Line Basics](#github-and-command-line-basics)
2. [Working with the site locally](#working-with-the-site-locally)
3. [Site Structure](#site-structure)
4. [Publishing updates](#publishing-updates)

## Github and Command Line Basics

Learn the basics for cloning a Github repo, pushing and pulling updates to/from the remote repository and command line for Mac and Windows users. See documentation: [Working with the Github Repo and Command Line](command-line.md)

## Working with the site locally

1. Install Jekyll and check other prerequisites following their documentation: [Jekyll Quickstart Guide](https://jekyllrb.com/docs/). Please see me if you'd like assitence with this step.

2. Clone this Git repository and change directory into the project folder:

```bash
git clone https://github.com/virginiaequitycenter/cville-equity-atlas.git
cd cville-equity-atlas
```

3. To install all the necessary gems specified in the `Gemfile.lock`, run Bundler:

```bash
bundle install
```

4. To build the site, run:

```bash
bundle exec jekyll serve
```

The site should build, and be locally accessible at [http://localhost:4000](http://localhost:4000).

## Site Structure

The Equity Atlas site follows the directory structure of a [Jekyll site](https://jekyllrb.com/docs/structure/). The repository is organized like this:

**[/_data](https://github.com/virginiaequitycenter/cville-equity-atlas/tree/main/_data):** This folder contains data files needed to run the site. Currently it includes [navbar.yml](https://github.com/virginiaequitycenter/cville-equity-atlas/blob/main/_data/navbar.yml) that provides the data for the site's primary navigation.

**[/_includes](https://github.com/virginiaequitycenter/cville-equity-atlas/tree/main/_includes):** This folder contains partial html files that are re-used throughout the site. This includes the content for site basics like the head metadata, header, footer, and navbar, as well as partials specific to implementing html/js for R packages used in reports. This includes leaflet, plotly, reactable, tabsets, and floating TOC. 

**[/_layouts](https://github.com/virginiaequitycenter/cville-equity-atlas/tree/main/_layouts):** This folder includes page templates for the site. Currently included are:
    * [default.html](): This is the default page template, and is currently used for the home page (index.html) as well as pages with embedded R Shiny apps.
    * [landing-page.html](): This template is used for site landing pages - Dashboards, Reports, Resources, and About
    * [report.html](): This is the template for Atlas reports generated from an R Markdown file.

**[/assets](https://github.com/virginiaequitycenter/cville-equity-atlas/tree/main/assets)**
    * [/css](): The styling for the site. SASS is used, see me for needed updates
    * [/img](): All image files for the site
    * [/js](): Javascript files for RMD produced reports

**[/docs](https://github.com/virginiaequitycenter/cville-equity-atlas/tree/main/docs):** This folder includes the documentation for the site, as well as the needed template file for the workflow from R to Jekyll ([atlas-rmd-template.html](https://github.com/virginiaequitycenter/cville-equity-atlas/blob/main/docs/atlas-rmd-template.html))

**[/pages](https://github.com/virginiaequitycenter/cville-equity-atlas/tree/main/pages):** This folder holds the site's content, organized as follows:
    * /dashboards
        * climate-dashboard.html (Cville Climate Equity Atlas, embedded R Shiny app)
        * cville-equity-dashboard.html (Cville Regional Equity Atlas, embedded R Shiny app)
        * index.html (Dashboards landing page)
    * /reports - below pages are reports produced from R Markdown files
        * albemarle-profile.html
        * index.html (Reports landing page)
        * orange-dot.html
        * school-composition.html
        * stepping-stones.html
        * stepping-stones-supplement.html
    * about.html (About landing page)
    * resources.html (Resources landing page)

**[_config.yml]():** The site's configuration settings. See [Jekyll documentation](https://jekyllrb.com/docs/configuration/).

**[index.html]():** This is the site's homepage

## Publishing Updates