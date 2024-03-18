# Enrichment Analysis workshop base
Updated on 2024


This is the source for the _Enrichment Analysis workshop_2024 website.
 
# Quickstart

```bash
# get hugo

brew install hugo

#download the theme and crete the right path

cd enrichment_analysis_workshop_2024
mkdir themes
cd themes
git clone https://github.com/matcornic/hugo-theme-learn.git

```

To update the site:

* Create or edit the Markdown in `content` (and possibly files in `static (for images)` or `config.toml`)
* Check that the site builds and looks correct by locally running `hugo server`.
* `git commit` your changes and `git push`.

Deployment to the live site at [monashbioinformaticsplatform.github.io/enrichment_analysis_workshop_2024/](https://monashbioinformaticsplatform.github.io/enrichment_analysis_workshop_2024/) happens after running `./deploy.sh` script

# Detail

## Dependencies

You'll need [Hugo](https://gohugo.io/getting-started/installing/).

## Cloning
```bash
git clone --recurse-submodules https://github.com/MonashBioinformaticsPlatform/enrichment_analysis_workshop.git
```

## Editing

```bash
hugo server

# or if you want to see pages marked as drafts
# hugo server -D
```

* Content is in `content/`
* Images and CSS are in `static/`
* Some theme customization and overrides lives in `layouts/`

### Updating for past / new events

We want past events to automatically appear as a list of 'posts' at the bottom of the events page. To do this:

* Create a new page in the `content/module` folder (eg `basics.md`). Include the date at the end of the file as shown.


## Custom template features

### In config.toml

```toml
# Add the page here

## Main menu
[[menu.main]]
    name = "Basics"
    weight = 100
    identifier = "basics"
    url = "/module/basics"

```




You need to build and deploy the live site manually, do:
```bash
# This builds the static pages, commits and pushes to the Github pages site (using the 'public' git submodule).
# It doesn't commit or push any changes to your Markdown source - do that yourself.

./deploy.sh
```


