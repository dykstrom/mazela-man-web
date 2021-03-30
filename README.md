# Mazela-Man

Tutorial website for FXGL, published as GoHugo website with GitHub Actions and Pages.

## GoHugo

Static website generator [Hugo](https://gohugo.io/).

### Theme

Uses the [Hugo-theme-learn](https://learn.netlify.app/en/).

Special layout components are explained on [learn.netlify.app/en/shortcodes](https://learn.netlify.app/en/shortcodes/notice/).

### Text format

All pages are separate md-files inside the [content](content/) directory. The formatting
of the text needs to use the rules specified in [commonmark.org](https://spec.commonmark.org/0.29/).

### Test locally

To test the site locally, first install Hugo as described on ["Install Hugo"](https://gohugo.io/getting-started/installing/).

Example for Mac:

```
brew install hugo
```

To run the site, open the terminal in the directory with the sources of this site and run the following command:

```
hugo serve
```

The website is now available on [localhost:1313](http://localhost:1313/).

### Build and run on GitHub Pages

Using a GitHub Action, the site is published on each commit into the "gh-pages" branch of this repository which is used
by GitHub Pages to publish the site.
