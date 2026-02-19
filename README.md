# static-tools

A collection of static tools and utilities. Inspired by [Simon Willison's tools site](https://tools.simonwillison.net/).

🔗 **Live site**: [tools.bobmaertz.com](https://tools.bobmaertz.com)

## About

This repository hosts a collection of standalone tools built with HTML, JavaScript, and WebAssembly. Each tool is self-contained in its own directory and accessible through a central landing page.

## Tools

### markdown-viewer
Renders Markdown documents with Mermaid diagram support. Paste, preview, and validate documentation directly in the browser.

### oauth-callback
A local development debug tool for inspecting OAuth 2.0 / OpenID Connect authorization callback parameters.

Point your OAuth server's redirect URI to this page (e.g., `https://tools.bobmaertz.com/oauth-callback`) to inspect every query parameter before the token exchange step.

**What it shows:**
- All query parameters from the callback URL
- Annotated RFC/spec references for known parameters:
  - `code`, `state` (RFC 6749)
  - `error`, `error_description`, `error_uri` (RFC 6749 error response)
  - `iss` — issuer identifier, mix-up attack protection (RFC 9207)
  - `session_state`, `id_token`, `access_token`, `token_type`, `expires_in`, `scope` (OpenID Connect)
- Human-readable description of standard `error` codes
- Copy-to-clipboard for individual values and the full URL

**Authorization code expiry timer:**
- Configurable countdown from 10 seconds to 10 minutes (default: 10 minutes)
- Color shifts green → amber → red as the code approaches expiry
- Start, pause, and reset controls
- Displays the projected expiry wall-clock time

**Why a static redirect URI instead of localhost?**
Most OAuth providers block `localhost` redirect URIs in production applications. Pointing the redirect to this public static page lets you capture and inspect the raw callback parameters from any environment without running a local server.

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

