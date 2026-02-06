Guidance for AI coding assistants working with this repository.

## Stack

Static HTML/CSS website. Task (Taskfile.yml) for operations. neocities gem for deployment.

## Commands

```bash
task setup              # Install dependencies (bundle install)
task format             # Format with prettier
task deploy             # Format then deploy (primary workflow)
task push               # Deploy only (uploads listed files)
task upload -- file     # Upload a specific file
task delete -- file     # Delete a file from the site
```

## Architecture

- Semantic HTML5 + single stylesheet
- No JavaScript or build process
- Direct file deployment
- Absolute paths in stylesheets
- Deployed files are explicitly listed in the `push` task;
  new files must be added there
- Google Fonts loaded via CSS (EB Garamond, Inter)
