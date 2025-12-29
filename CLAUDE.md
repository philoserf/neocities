# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a static website project for Neocities hosting. The site is a personal landing page with minimal structure:

- `index.html` - Main landing page
- `not_found.html` - 404 error page
- `style.css` - Shared stylesheet
- `robots.txt` - Search engine directives

## Build and Development

This project uses Task (Taskfile.yml) for common operations:

```bash
task setup    # Install Ruby dependencies (neocities gem)
task format   # Format files with Prettier
```

The `neocities` Ruby gem (via Bundler) is used for deployment to Neocities hosting.

## Publishing to Neocities

The `neocities` CLI provides commands for managing and deploying the site:

```bash
neocities push .        # Deploy entire directory to Neocities
neocities upload FILE   # Upload specific file(s)
neocities delete FILE   # Delete file(s) from site
neocities list          # List files currently on site
neocities info          # View site statistics
```

The `push` command is the primary deployment method - it recursively uploads the current directory to your Neocities site. Authentication is handled via API key (stored after first login).

## Architecture

The site follows a simple static HTML structure with:

- Semantic HTML5 markup
- Single shared stylesheet (`/style.css`)
- No JavaScript or build process required
- Direct file deployment model (no compilation/bundling)

All HTML files link to `/style.css` with absolute paths for consistency across the site structure.
