# static-tools

A collection of static tools and utilities. Inspired by [Simon Willison's tools site](https://tools.simonwillison.net/).

🔗 **Live site**: [tools.bobmaertz.com](https://tools.bobmaertz.com)

## About

This repository hosts a collection of standalone tools built with HTML, JavaScript, and WebAssembly. Each tool is self-contained in its own directory and accessible through a central landing page.

## Structure

```
/
├── index.html              # Landing page
├── tool-name/             # Individual tool directories
│   └── index.html
└── .github/workflows/
    └── deploy.yml         # Cloudflare Pages deployment
```

## Adding a Tool

1. Create a new directory for your tool
2. Add an `index.html` and any required static assets (JS, WASM, CSS, etc.)
3. Update the root `index.html` to link to your new tool
4. Commit and push to `main` for automatic deployment

## Deployment

- **Main branch**: Automatically deploys to production
- **Other branches**: Manual deployment available via GitHub Actions for staging/preview

