# joanna-mazurek.com

![CI](https://github.com/joannofjoy/joanna-mazurek.com/actions/workflows/ci.yml/badge.svg)

Personal portfolio site for Joanna Mazurek — Data Analyst, BI Professional, and Researcher
working at the intersection of data, psychology, and social impact.

**Live site:** [joanna-mazurek.com](https://joanna-mazurek.com)

## Tech stack

Plain HTML5 and CSS3 — no framework, no build step, no client-side JavaScript.

## Project structure

```
.
├── index.html              # Page markup
├── assets/
│   ├── css/styles.css      # All styling
│   └── img/favicon.svg     # Favicon
├── .github/workflows/ci.yml  # Lint + link-check on every push/PR
├── CNAME                   # GitHub Pages custom domain
└── package.json            # Dev-only tooling (linting), not runtime dependencies
```

## Running locally

No build step — just open `index.html` in a browser, or serve it:

```bash
npx serve .
```

## Linting

```bash
npm install
npm run lint
```

Runs `stylelint` against `assets/css/` and `html-validate` against `index.html`. The same
checks run automatically in CI on every push and pull request, along with a link checker.

## Notes

- The EU Migration Dashboard is a Microsoft Power BI "Publish to Web" embed. Publish-to-web
  reports are, by Microsoft's design, viewable by anyone with the link — that's intentional
  here since it's a public portfolio piece, not a data leak.
- GitHub Pages doesn't support custom HTTP response headers, so header-based protections
  (HSTS, X-Frame-Options, etc.) rely on GitHub Pages' platform defaults; a
  `Content-Security-Policy` is set via a `<meta>` tag in `index.html` as an additional layer.

## License

[MIT](LICENSE)
