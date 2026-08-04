# calebschmotter.com

Personal academic website for Caleb H. Schmotter, Visiting Assistant Professor of Political Science at St. Olaf College. Built as a static site with [Quarto](https://quarto.org) and published via GitHub Pages.

## Structure

```
├── _quarto.yml          site config: navigation, footer, theme
├── styles.scss           visual design — palette, typography, layout
├── _includes/fonts.html  web font loading
├── index.qmd             home
├── about.qmd              bio, education, grants, office hours
├── research.qmd          book projects, articles, working papers
├── teaching.qmd          philosophy, simulations, labs, courses, awards
├── images/                headshot, favicon
├── cv/                    CV PDF
├── files/                 sample syllabus PDF
└── docs/                  rendered site (published, generated — do not edit)
```

## Stack

Quarto → static HTML, no server, no database. Fonts are Fraunces (headings) and IBM Plex Sans/Mono (body, labels), loaded from Google Fonts. No JavaScript framework; a handful of custom SCSS classes handle layout.

## Local development

```bash
quarto preview   # live-reloading local server
quarto render    # builds docs/ for publishing
```

## License

Site design and code: no license granted for reuse. Written content is © Caleb H. Schmotter.
