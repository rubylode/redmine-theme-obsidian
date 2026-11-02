# Rubylode Obsidian for Redmine

A theme for Redmine 7 and up: a white page with hairlines, one indigo-blue, small corners and state circles and priority squares in the issue list.

It is plain CSS plus one small script (`javascripts/theme.js`, about 45 lines), with no plugin, no build step and no change to
Redmine itself. The script only reads the page: it puts a status dot beside the group name in an issue list grouped by status,
and gives the top bar a hairline shadow once the page scrolls. Without it the theme still works. It is built on the shared Rubylode
theme base, so it covers the same pages as the other Rubylode themes and styles the Rubylode plugins.

Light and dark are equal here. Dark follows your system setting (see [Dark mode](#dark-mode)).

![A walk through Rubylode Obsidian: the project, the issue list, an issue, the wiki, the to-do page and the new issue form](docs/demo/walkthrough-light.gif)

| | |
|---|---|
| ![The issue list](docs/screenshots/issues-light.png) | ![An issue](docs/screenshots/issue-light.png) |
| ![The new issue form](docs/screenshots/new-issue-light.png) | ![The project overview, with the Rubylode Projects plugin](docs/screenshots/project-light.png) |
| ![The projects list, with the Rubylode Projects plugin](docs/screenshots/projects-light.png) | ![My page, with the Rubylode Home plugin](docs/screenshots/my-page-light.png) |
| ![The welcome page, with the Rubylode Home plugin](docs/screenshots/home-light.png) | ![A status block, from the Rubylode Uptime Kuma plugin](docs/screenshots/service-status-light.png) |
| ![The Stats page, with the Rubylode Stats plugin](docs/screenshots/stats-light.png) | ![The to-do page, with the Rubylode To-do plugin](docs/screenshots/todo-light.png) |

Dark mode:

![A walk through Rubylode Obsidian in dark mode](docs/demo/walkthrough-dark.gif)

| | |
|---|---|
| ![The issue list in dark mode](docs/screenshots/issues-dark.png) | ![An issue in dark mode](docs/screenshots/issue-dark.png) |
| ![The new issue form in dark mode](docs/screenshots/new-issue-dark.png) | ![The project overview in dark mode](docs/screenshots/project-dark.png) |
| ![The projects list in dark mode](docs/screenshots/projects-dark.png) | ![My page in dark mode](docs/screenshots/my-page-dark.png) |
| ![The welcome page in dark mode](docs/screenshots/home-dark.png) | ![A status block in dark mode](docs/screenshots/service-status-dark.png) |
| ![The Stats page in dark mode](docs/screenshots/stats-dark.png) | ![The to-do page in dark mode](docs/screenshots/todo-dark.png) |

The screenshots come from the demo Redmine in this repository; the people, projects and issues in it are made up.

## Contents

- [What it looks like](#what-it-looks-like)
- [Install](#install)
- [What is covered](#what-is-covered)
- [Rubylode plugins](#rubylode-plugins)
- [Customising](#customising)
- [Dark mode](#dark-mode)
- [Accessibility](#accessibility)
- [Compatibility](#compatibility)
- [Development](#development)
- [Checks and releases](#checks-and-releases)
- [License](#license)

## What it looks like

- A white page, and white panels told apart by hairlines instead of shadows. Greys have almost no tint, and the only colour
  that stays is one indigo-blue for links, selected items, focus and the main action.
- A two-row header on a white ground. The top bar holds a small indigo-to-violet mark, the global links, the search and project
  switcher, and your avatar. Below it, the project name and its tabs, the current one underlined in indigo.
- The issue list marks status with a circle (empty for New, half for In Progress and Feedback, full for Resolved, Closed and
  Rejected) and priority with a small square, as plain cells. Rows have hairlines and faint stripes, and hover is a pale indigo.
- On the issue page, status and priority are chips, and the card has an edge in the status colour.
- Corners are 6px nearly everywhere and type is 13px. Rows are a little tighter than in the other Rubylode themes.

## Install

1. Download the zip attached to the latest release (the Releases page of this repository) and unzip it inside the `themes` folder of your Redmine, so that `themes/obsidian/stylesheets/application.css` exists. Or clone this repository and copy (or link) its `obsidian` folder into `themes/`.
2. Restart Redmine.
3. In Administration, Settings, Display, choose **Obsidian** as the theme and save.

To go back, choose another theme on the same page. Nothing is written to the database apart from that setting.

The theme folder holds the stylesheets, `javascripts/theme.js` and the mark (`images/obsidian-mark.svg`). It ships no fonts: it
asks for Inter and falls back to the system's own.

## What is covered

The page check loads these pages, in light and dark, at desktop and phone width: sign in, the home page, the project
overview (Redmine's own and the Rubylode Projects plugin's), the projects list, the issue list (plain and grouped), activity, the
roadmap, an issue, an issue with subtasks, a child issue, the edit and new issue forms, the to-do page, the Stats page, the pages
of the four status plugins, My page (Redmine's own and the Rubylode Home plugin's), a wiki page and its editor, spent time, Gantt,
the calendar, project settings and administration.
Flash messages, tabs, the right-click menu, dropdowns, pagination, the text editor and the phone slide-out menu are styled as well.

<!-- rubylode-plugins:start -->
## Rubylode plugins

Rubylode Obsidian styles the Rubylode plugins' blocks natively. Each plugin draws with its own CSS custom properties, and one section of the
theme, `obsidian/stylesheets/plugins.css`, points them at Rubylode Obsidian's tokens, so the blocks follow the theme in light and dark:

- [Rubylode Projects](https://github.com/rubylode/redmine-rubylode-projects) (`--rubylode-projects-*`): the overview cards and the projects list.
- [Rubylode Home](https://github.com/rubylode/redmine-rubylode-home) (`--rubylode-home-*`): My page and the welcome page.
- [Rubylode To-do](https://github.com/rubylode/redmine-rubylode-todo) (`--todo-*`): the to-do page.
- [Rubylode Uptime Kuma](https://github.com/rubylode/redmine-rubylode-uptime-kuma) (`--rubylode-uptime-kuma-*`),
  [Rubylode GlitchTip](https://github.com/rubylode/redmine-rubylode-glitchtip) (`--rubylode-glitchtip-*`),
  [Rubylode Windmill](https://github.com/rubylode/redmine-rubylode-windmill) (`--rubylode-windmill-*`) and
  [Rubylode Beszel](https://github.com/rubylode/redmine-rubylode-beszel) (`--rubylode-beszel-*`): the status blocks.
- [Rubylode Stats](https://github.com/rubylode/redmine-rubylode-stats) (`--stats-tooltip-*`): the chart tooltip.
- [Rubylode New issue button](https://github.com/rubylode/redmine-rubylode-new-issue-button): a rounded primary button beside the search.
  Plugins load their stylesheets after the theme's, so these rules start with `body #header` to win whatever the order.

None of them is needed. Without a plugin its rules match nothing.
<!-- rubylode-plugins:end -->

## Customising

Every colour, corner, shadow, font and a few sizes are custom properties in `obsidian/stylesheets/tokens.css` (light values) and
`obsidian/stylesheets/dark.css` (dark values). Change them there, or override them from a stylesheet of your own. The names
start with `--theme-` and are the same in every Rubylode theme. The main ones:

| Token | What it is |
|---|---|
| `--theme-page`, `--theme-surface`, `--theme-surface-sunken`, `--theme-surface-hover` | the page, the panels, sunken panels and stripes, hovered rows |
| `--theme-line`, `--theme-line-soft`, `--theme-line-strong` | panel borders and row lines, column lines, field borders |
| `--theme-ink`, `--theme-ink-soft`, `--theme-ink-muted` | text, secondary text, labels and notes |
| `--theme-accent-0` to `--theme-accent-9` | the indigo-blue ramp; `--theme-link`, `--theme-primary` and Redmine's blue ramp point into it |
| `--theme-status-new`, `-in-progress`, `-resolved`, `-feedback`, `-closed`, `-rejected` | status colours, by Redmine's default status ids 1 to 6 |
| `--theme-success`, `--theme-warning`, `--theme-danger`, `--theme-danger-strong` | meaning colours (priority High, Urgent, Immediate) |
| `--theme-radius-small`, `--theme-radius`, `--theme-radius-panel`, `--theme-radius-pill` | corners of fields, cards, panels and chips |
| `--theme-border-width`, `--theme-border-style`, `--theme-density` | panel borders, and the height of table rows and list items |
| `--theme-font`, `--theme-font-monospace`, `--theme-title-font`, `--theme-title-weight` | the text, code and heading fonts |

The rest (messages, avatars, diffs, the Gantt chart, the header heights, the icons drawn in the stylesheet) are listed with a
comment each in `tokens.css`. If you used the old `--obsidian-*` names, the rename table is in the changelog.

Obsidian's own touches that tokens cannot express (the 13px type, the state circles and priority squares, the tab size) are
in `obsidian/stylesheets/flourishes.css`, loaded last.

Status and priority colours are matched by Redmine's default ids (statuses 1 New to 6 Rejected, priorities 1 Low to 5
Immediate). If yours differ, change the ids in the issue list sections of `obsidian/stylesheets/structure.css` and in
`flourishes.css`.

## Dark mode

Dark mode follows your system setting (`prefers-color-scheme`): near-black with a cool tint, panels a step lighter than the page,
light ink, and the indigo lifted so it reads on dark. Code blocks stay light, since Redmine's syntax colours are made for a
light background. To keep Obsidian light-only, remove the line `@import url(dark.css);` from `obsidian/stylesheets/responsive.css`;
every dark value is in that one file.

## Accessibility

Text and controls meet WCAG AA in both modes. The page check measures every visible text against the colour behind it on every
page; the tokens were also measured one by one, including the parts the check cannot see (field borders, focus rings, chips
on a hovered row). The measured ratios are in [docs/accessibility.md](docs/accessibility.md). In short: body text 18.1:1 in light
and 15.6:1 in dark, secondary text at least 5.9:1 and 6.6:1, links at least 4.9:1 and 6.0:1, white on the primary at least
5.5:1, every status and priority chip at least 4.8:1, field borders at least 3.4:1 and focus rings at least 4.0:1.

## Compatibility

Redmine 7.0 and newer. Tested on 7.0.2, from both the `7.0.2` and the `7.0` image tags (on 2026-11-02 the 7.0 line was at 7.0.2). Older versions are not expected to work: Redmine 7 reads a theme from `themes/<name>` and is
built on the Open Color variables this theme remaps.

Browsers: current Chrome, Edge, Firefox and Safari. The theme uses `:has()` and `color-mix()` (Chrome 111, Firefox 121,
Safari 16.4 and newer); an older browser shows plainer status chips and keeps the rest.

## Development

You need Docker, Ruby, Node and Chrome.

```
npm install
ruby bin/demo up        # a throwaway Redmine with demo data at http://localhost:3105 (admin / admin)
npm run check           # loads every page in light and dark, at desktop and phone width
npm run screenshots     # docs/screenshots
npm run record          # docs/demo, a GIF of a walk through the pages
ruby bin/demo reset     # wipe the demo
```

If copies of the Rubylode plugins listed above sit next to this repository (`../redmine-rubylode-todo` and so on, or in a folder
named in `RUBYLODE_PLUGINS_DIR`), the demo mounts them and the check, screenshots and recording show their pages. The demo points
the status plugins at an address where nothing answers, so their pages show the "unavailable" state. Without the plugins the
demo is plain Redmine, and the check skips their pages.

The stylesheets (except `flourishes.css`), `javascripts/theme.js`, `test/`, `bin/demo` and `docker-compose.yml` are generated from the base all Rubylode
themes share, so a fix there reaches every theme. If you send a change to one of them, I will carry it over to the base.

The check fails on console errors, failed requests, sideways scrolling and text below WCAG AA contrast. `REDMINE_TAG=7.0 ruby bin/demo up`
runs it against another Redmine version. After you change a stylesheet, run `ruby bin/demo restart` and reload: Redmine caches theme
files until it restarts.

## Checks and releases

Every push starts a real Redmine from its Docker image (7.0.2 and the 7.0 line), loads every page of the theme in light and dark at desktop and phone width, and fails on console errors, failed requests, sideways scrolling and low text contrast. On GitHub that is `.github/workflows/check.yml`, on GitHub's own runners, and it also runs on pull requests. On a self-hosted Gitea it is `.gitea/workflows/check.yml`, which runs only on pushes to `main`, because that runner works on the host with Docker access and must only run code that is already merged.

A tag such as `v2.0.0` runs the same check, builds `obsidian-<version>.zip` holding the theme folder, and attaches it to a release with the matching section of `CHANGELOG.md` as its notes (`release.yml` in the same folders). The tag needs a section for that version in the changelog. More on both, and on the drift check that compares the generated files with the shared base, in [docs/ci.md](docs/ci.md).

## License

GPL version 2 or later, the same as Redmine. See `LICENSE`. Copyright (C) 2026  Nick Gorbikoff.

No warranty, as the GPL says. Try it on a copy of your tracker before the real one.
