# Changelog

All notable changes to this theme. The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

## [2.1.3] - 2026-11-03

### Added

- The theme now has a Rubylode thumbnail, shown at the top of the README. The theme itself is unchanged.

## [2.1.2] - 2026-11-03

### Changed

- The chart colours are now a muted editorial set.

## [2.1.1] - 2026-11-02

### Added

- The theme defines the chart colour tokens the Stats plugin reads.

## [2.1.0] - 2026-11-02

### Changed

- The palette is black, white and grey. No blue or indigo is left in the chrome.
- Links are in the ink colour with a thin grey underline, which turns to the ink colour on hover. Table headings, tabs, the action bars, pagination and issue ids are not underlined.
- The selected sidebar item and the selected view switch are a light grey fill (`#ebebeb`) with black text. In dark they are white on `#2a2a2a`.
- The Save, Apply and New issue buttons, and the "+" button, are black with white text. In dark they are `#f0f0f0` with black text.
- The focus ring is black, with a grey halo. In dark it is `#f0f0f0`.
- The selected tab underline is black, white in dark. Checkboxes and radio buttons are black.
- The project mark and the sidebar tile are a black to dark grey square. In dark they are light grey, from the new `obsidian-mark-dark.svg`.
- Hovered rows are `#f0f0f0` and the grey ramp has no tint. Dark surfaces are neutral near-black, with no blue in them.
- Status New is grey and Feedback is dark grey (light grey in dark). Initials use plum, dark grey, green, brown, red and olive. Red, green and amber keep their meaning.
- The code block, the selection and the search highlight are neutral or amber, with no violet.
- Contrast was measured again in both modes: every text pair is 4.5:1 or more. See `docs/accessibility.md`.

### Token meaning changes

- `--theme-accent-0` to `--theme-accent-9` are a grey ramp, not an indigo-blue ramp. Redmine's blue ramp (`--oc-blue-*`) points into it.
- `--theme-link` is the ink colour, not blue. `--theme-primary` and `--theme-primary-background` are near-black, and white in dark, with `--theme-ink-on-primary` set to black in dark.
- `--theme-secondary` is a light grey and is no longer violet. `--theme-sidebar-tile` is a gradient from black to dark grey.
- `--theme-mark-image` has a dark value that points to `obsidian-mark-dark.svg`.

## [2.0.1] - 2026-11-02

### Changed

- The base text size is 16px, up from 13px. It is the token `--theme-font-size`.
- List text is 14px, up from 10.6px. The sidebar is 14px, up from 11.4px. Fields and buttons are 15px, up from 13.3px.
- Labels, chips, headings, the header, the project tabs and the action buttons grew in the same proportion.
- `--theme-font` starts with the bundled Noto Sans, in place of Inter, and `--theme-font-monospace` with the bundled Noto Sans Mono. The woff2 files and their SIL Open Font License 1.1 texts are in `obsidian/fonts/`.
- In the sidebar layout, issue list cells have 8px of padding at each side and the subject wraps down to 9em, so the list fits at 1280px.
- The project switcher in the top bar is 184px wide, up from 160px.

### Fixed

- On pages with no project menu, such as My page and the welcome page, the sidebar now holds the global links (Home, My page, Projects, Administration for an administrator, Help). They leave the top bar there, so they show once.
- Redmine's right-hand sidebar is 200px wide in the sidebar layout, down from 260px.
- The subject column of the issue list wraps down to 10em in the sidebar layout, so the list fits beside both sidebars at 1280px and the dates are no longer cut off.
- A list that is still too wide scrolls sideways inside its wrapper, and its right edge fades while there is more to scroll to.

## [2.0.0] - 2026-11-02

### Changed

- The theme is now built on the shared Rubylode theme base. The single stylesheet is replaced by `tokens.css`, `structure.css`, `plugins.css`, `dark.css` and `flourishes.css`, loaded from `application.css` and `responsive.css`.
- The Rubylode plugins now take the theme's colours: Projects, Home, To-do, Uptime Kuma, GlitchTip, Windmill, Beszel, Stats and the New issue button.
- The pages the old stylesheet left to Redmine are now styled: the home page, the project overview, My page, the roadmap, an issue with subtasks, the Gantt chart, the calendar, spent time, project settings and administration.
- The full-height sidebar is kept on screens 1100px and wider, now 216px wide and set by the base's sidebar tokens. It holds the project name behind the indigo-to-violet tile and the project menu, or the administration menu. A thin bar across the top holds the global links, the New issue button, the search, the project switcher and the account. The selected item is a pale indigo tint with no edge bar, as before.
- From 900px to 1099px the header is the base's two rows, on a white ground: the mark, the global links, the search and the account, then the project name and its tabs. Below 900px it is Redmine's phone layout. The sign-in page keeps the two rows at every width.
- The mark is the small indigo-to-violet square. It is the tile before the project name in the sidebar, and in `images/obsidian-mark.svg` for the top bar of the two-row header and the sign-in page.
- Type is 13px, and the project tabs are 13px, so a project with many modules still fits at 1100px.
- Field and button borders are darker (`#868b9b` in light) so that they reach 3:1 against the page, as WCAG asks of controls.
- In dark, panels are a step lighter than the page. They used to be the same colour as it.
- Closed is a full green circle again and New an empty grey one, as in 1.0.0. Resolved is a full green circle too.
- Status and priority on the issue page are chips with a dot and a bar meter, as in the base.
- `javascripts/theme.js` now tags status groups and the scrolled header, and ends with Obsidian's own script. The base's script comes first, so the old one is replaced.
- The date chips, the assignee initials and the Issues, Gantt, Calendar and Activity switch above the list are kept. They are added by the script, and the theme works without it. Their colours are the new `--theme-initials-0` to `--theme-initials-5` and `--theme-date-chip-border` tokens.

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
| `--obsidian-sidebar-width` | `--theme-sidebar-width` |
| `--obsidian-phone-menu`, `--obsidian-phone-menu-ink` | none; the phone menu uses `--theme-surface` and `--theme-ink` |
| `--oc-gray-0` to `--oc-gray-9` | `--theme-neutral-0` to `--theme-neutral-9` |
| `--oc-white` | `--theme-redmine-white` |
| `--oc-blue-0` to `--oc-blue-6`, `--oc-indigo-*` | `--theme-accent-0` to `--theme-accent-6` |
| `--oc-blue-7` | `--theme-redmine-accent` |
| `--oc-blue-9` | `--theme-link` |
| `--fonts-main` | `--theme-font` |

The `--oc-*` variables still exist, because Redmine reads them, but the theme sets them from the `--theme-*` tokens. Change the
token, not the variable. Every token is listed in the README and commented in `tokens.css`.

### Accessibility

- The page check now loads 29 pages with every Rubylode plugin mounted: 116 runs in light and dark, at desktop and phone width, with no console errors, no failed requests, no sideways scrolling and no text below AA. The widths between, 900px to 1100px, were loaded the same way. The measured ratios are in `docs/accessibility.md`.

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
