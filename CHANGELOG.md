# Changelog

All notable changes to this theme. The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

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
