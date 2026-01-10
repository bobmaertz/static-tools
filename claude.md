# Static Tools Project

## Overview
A collection of static tools and utilities hosted at tools.bobmaertz.com. This project serves as a landing page for various standalone tools built with HTML, JavaScript, and WebAssembly.

## Inspiration
Inspired by [Simon Willison's tools site](https://tools.simonwillison.net/)

## Project Structure
```
/
├── index.html              # Landing page with links to all tools
├── tool-name/             # Each tool in its own directory
│   ├── index.html
│   └── (tool-specific files: JS, WASM, CSS, etc.)
└── .github/workflows/
    └── deploy.yml         # Cloudflare Pages deployment workflow
```

## Deployment

### Automatic Deployment
- Pushes to `main` branch automatically deploy to production via Cloudflare Pages

### Manual Deployment
- Other branches can be manually deployed for staging/preview
- Navigate to GitHub Actions → "Deploy to Cloudflare Pages" → "Run workflow"
- Choose the branch and environment (preview or production)

### Required Secrets
The workflow requires two repository secrets:
- `CLOUDFLARE_API_TOKEN`
- `CLOUDFLARE_ACCOUNT_ID`

## Adding New Tools

1. Create a new directory for your tool (e.g., `/my-tool/`)
2. Add an `index.html` and any required static assets
3. Update the root `index.html` to link to the new tool
4. Commit and push to deploy

### Tool Guidelines
- Tools should be self-contained within their directory
- Use static content: HTML, JavaScript, WebAssembly

## Technology Stack
- **Hosting**: Cloudflare Pages
- **CI/CD**: GitHub Actions
- **Content**: Static HTML, JS, WASM
- **Starting Point**: Simple index.html landing page
