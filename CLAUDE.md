# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Stack

Static HTML/CSS site deployed to Neocities. Task (`Taskfile.yml`) wraps the `neocities` Ruby gem. Formatting via Prettier through `bunx` (Bun, not npm).

## Commands

```bash
task            # default → bundle install, then neocities info + git status
task setup      # bundle install
task format     # bunx prettier --write --ignore-unknown .
task push       # upload the four deployed files
task deploy     # format, then push (primary publish workflow)
task list       # list files currently on Neocities
task info       # site stats
task upload -- <files>   # upload arbitrary files
task delete -- <files>   # delete from Neocities
```

## Architecture

- Semantic HTML5 + a single `style.css`. No JavaScript, no build step.
- Deployed files are explicitly enumerated in the `push` task: `index.html`, `not_found.html`, `style.css`, `robots.txt`. **Any new file intended for deployment must be added to that list** — `push` does not glob.
- Stylesheet uses absolute paths (`/style.css`) so it resolves on both `/` and `/not_found.html`.
- Fonts (EB Garamond, Inter) loaded via `@import` from Google Fonts at the top of `style.css`.
- Deployment auth: the `neocities` gem reads credentials from its own config (`~/.neocities/config`) — not committed here.
