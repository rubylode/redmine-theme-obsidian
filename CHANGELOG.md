# Changelog

All notable changes to this theme. The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

## [2.0.0] - 2026-11-02

### Changed

- The theme is now built on the shared Rubylode theme base. The single stylesheet is replaced by `tokens.css`, `structure.css`, `plugins.css`, `dark.css` and `flourishes.css`, loaded from `application.css` and `responsive.css`.
- The Rubylode plugins now take the theme's colours: Projects, Home, To-do, Uptime Kuma, GlitchTip, Windmill, Beszel, Stats and the New issue button.
- The pages the old stylesheet left to Redmine are now styled: the home page, the project overview, My page, the roadmap, an issue with subtasks, the Gantt chart, the calendar, spent time, project settings and administration.
- The header is the base's two rows, on a white ground: the top bar with the mark, the global links, the search and the account, and the project name and tabs below it.
- The full-height sidebar on screens 1100px and wider is gone. The project tabs sit in the second header row at every width.
- The mark in the top bar is the small indigo-to-violet square the old sidebar showed before the project name, now in `images/obsidian-mark.svg`.
- Type is 13px, and the project tabs are 13px, so a project with many modules still fits at 1100px.
- Field and button borders are darker (`#868b9b` in light) so that they reach 3:1 against the page, as WCAG asks of controls.
- In dark, panels are a step lighter than the page. They used to be the same colour as it.
- Closed is a full grey circle and Resolved a full green one. New is a blue empty circle. Closed used to be green and New grey.
- Status and priority on the issue page are chips with a dot and a bar meter, as in the base.
- `javascripts/theme.js` now tags status groups and the scrolled header. The base's script replaces the old one.

### Removed

- The date chips, the assignee initials and the Issues, Gantt, Calendar and Activity switch above the list. They came from the old script, which the base's script replaces.

### Migration

The token names changed, so a stylesheet of your own that overrides `--obsidian-*` or the `--oc-*` variables needs the new names:

| Old name | New name |
|---|---|
| `--obsidian-page` | `--theme-page` |
| `--obsidian-sidebar` | `--theme-surface-sunken` |
| `--obsidian-line` | `--theme-line` |
| `--obsidian-radius` | `--theme-radius-small` |
| `--obsidian-shadow` | `--theme-shadow-popup` (the colour is inside the value) |
| `--obsidian-blue-0` to `--obsidian-blue-8` | `--theme-accent-0` to `--theme-accent-8` |
| `--obsidian-sidebar-width`, `--obsidian-phone-menu`, `--obsidian-phone-menu-ink` | none; the sidebar is gone and the phone menu uses `--theme-surface` and `--theme-ink` |
| `--oc-gray-0` to `--oc-gray-9` | `--theme-neutral-0` to `--theme-neutral-9` |
| `--oc-white` | `--theme-redmine-white` |
| `--oc-blue-0` to `--oc-blue-6`, `--oc-indigo-*` | `--theme-accent-0` to `--theme-accent-6` |
| `--oc-blue-7` | `--theme-redmine-accent` |
| `--oc-blue-9` | `--theme-link` |
| `--fonts-main` | `--theme-font` |

The `--oc-*` variables still exist, because Redmine reads them, but the theme sets them from the `--theme-*` tokens. Change the
token, not the variable. Every token is listed in the README and commented in `tokens.css`.

### Accessibility

- The page check now loads 29 pages with every Rubylode plugin mounted: 116 runs in light and dark, at desktop and phone width, with no console errors, no failed requests, no sideways scrolling and no text below AA. The measured ratios are in `docs/accessibility.md`.

### Tooling

- The check, screenshots and recording scripts, the demo data and `bin/demo` come from the base, so the demo mounts every Rubylode plugin it finds.
- The Gitea workflows run manual checks only on `main`, check that a release tag is on `main` and keep the release token out of the job that runs the repository's code.
- The README screenshots and both walkthroughs are retaken, with the plugin pages.

## [1.0.0] - 2026-10-26

### Added

- Obsidian theme: near-neutral greys, hairlines and one indigo-blue. The colours come from the Open Color variables Redmine 7 uses.
- On screens 1100px and wider, a full-height sidebar on the left holds the project and its menu (or the administration menu), and a thin bar over the page holds the general links, search, project jump and profile, in plain CSS. Narrower screens and the login page keep Redmine's own layout.
- The issue list gets small state circles (empty, half, full) and priority squares from the row's own classes, tinted status group bars, hairline rows, a chip round each date, round initials for the assignee and a switch for Issues, Gantt, Calendar and Activity. The chips, the initials and the switch come from `javascripts/theme.js`, which only reads the page.
- Activity is a feed with a small date label and hairline rows.
- Faint stripes and hairline column lines in tables, a flat issue card and a login card.
- A dark set for the system dark setting, in one block at the end of the stylesheet.
- The theme skeleton, the demo Redmine, the page check, the screenshot script and the recorder.
- Tested on Redmine 7.0.2 and the 7.0 line, in light and dark, at desktop and phone width. No console errors, failed requests or sideways scrolling, and text at AA contrast on the pages that matter: the wiki, the activity page and the Rubylode to-do page.
