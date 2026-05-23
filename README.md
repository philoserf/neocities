# neocities

A personal brochure site on [Neocities](https://neocities.org), published at <https://philoserf.neocities.org>.

Static HTML and CSS — no JavaScript, no build step. Deployed with the [`neocities`](https://rubygems.org/gems/neocities) Ruby gem, orchestrated by [Task](https://taskfile.dev).

## Deploy

```sh
task deploy
```

Formats files with Prettier, then uploads the four files listed in `Taskfile.yml` under the `push` target. New files intended for deployment must be added to that list — there is no glob.

Other targets:

| Task                     | Action                           |
| ------------------------ | -------------------------------- |
| `task`                   | `neocities info` + `git status`  |
| `task setup`             | `bundle install`                 |
| `task format`            | Prettier (via `bunx`)            |
| `task push`              | Upload the listed files          |
| `task list`              | List files currently on the site |
| `task info`              | Site statistics                  |
| `task upload -- <files>` | Upload specific files            |
| `task delete -- <files>` | Delete files from the site       |

## Credentials

The `neocities` gem authenticates one of two ways:

- **API key in the environment.** Set `NEOCITIES_API_KEY` — useful for CI or ephemeral shells.
- **Stored config.** The first run of `neocities upload` (or any authenticated command) prompts for sitename and password, then writes an API key to `~/Library/Application Support/neocities/config.json`.

`neocities logout` removes the stored key.

## Licenses

- Code: [MIT](LICENSE)
- Site content (text, prose): see [CONTENT-LICENSE.md](CONTENT-LICENSE.md)
