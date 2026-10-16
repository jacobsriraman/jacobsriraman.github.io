# Updating your website

The site is one page: an introduction, recent news, and contact links. There are
no publication or CV tabs to maintain. The writing TODOs are YAML comments and
never show up on the website.

## Make it sound like you

Edit `_data/home.yml`:

- `intro` and `about`: a short introduction in your own voice. The current copy is
  a factual starting point from your previous homepage and CV.
- `currently`: an optional sentence about something on your mind.
- `personal`: an optional paragraph about life outside research. The entire
  section is hidden until you write something.
- `portrait`: an optional image path, such as `/images/jacob.jpg`. Add that image
  to the repository first, and update `portrait_alt` if needed.
- `cv_url`: optionally add `/files/cv.pdf` after putting a PDF there. This adds
  a small footer link. Your LaTeX source is excluded from the published site.

Use Markdown for links and emphasis. Keep the indentation; use `>-` for text
spanning multiple lines, following the existing examples. Use `""` to leave an
optional field blank. If your introduction changes, update `description` in
`_config.yml` too; that is the short description used in search and link previews.

## Post news

Add an entry to `_data/news.yml`:

```yaml
- date: "2026-10"
  text: >-
    A sentence about something you did, started, made, or learned.
    You can include a [link](https://example.com).
```

The five most recent updates appear automatically, sorted by month. Use a
quoted `YYYY-MM` date. The starting updates come from your CV; review their
wording before publishing. You do not need a publication to post an update.
Set the file contents to `[]` to hide the news section and its navigation link.

Contact details live under `author` in `_config.yml`. Layout and styling live in
`_layouts/personal.html`, `_pages/about.md`, and `assets/css/personal.css`.

## Preview and publish

This remains a standard Jekyll / GitHub Pages site. With Ruby, Bundler, and Ruby
development headers installed:

```sh
bundle install
bundle exec jekyll serve
```

Open `http://localhost:4000`. On systems that name the Bundler command `bundle3.2`,
use that in place of `bundle`. To check production output:

```sh
JEKYLL_ENV=production bundle exec jekyll build
```

Publish through your existing GitHub Pages branch workflow. The redesign does
not change hosting. Old `/about/`, `/publications/`, `/talks/`, and `/cv/` links
redirect to the homepage. Unused Academic Pages examples remain in the repository
for reference, but `_config.yml` excludes them from the published site.
