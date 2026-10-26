# Changelog

All notable changes to this theme. The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

## [Unreleased]

### Added

- Obsidian: near-neutral greys, hairlines and one indigo-blue, in the Open Color variables Redmine 7 is built on.
- On screens 1100px and wider, a sidebar runs the full height on the left, holding the project and its menu (or the administration menu), and a thin bar over the page holds the general links, search, project jump and profile, in plain CSS. Narrower screens and the login page keep Redmine's own layout.
- The issue list uses small state circles (empty, half, full) and priority squares from the row's own classes, tinted status group bars, hairline rows, a chip round each date, round initials for the assignee, and Issues, Gantt, Calendar and Activity as a switch above the list. The chips, initials and switch come from one small script, `javascripts/theme.js`, which only reads the page.
- Activity is a quiet feed: a small date label, then rows with hairlines.
- Faint stripes and hairline column lines in tables, a flat issue card, a login card.
- A dark set for the system dark setting, in one block at the end of the stylesheet.
- The theme skeleton, the demo Redmine, the page check, the screenshot script and the recorder.
- Tested on Redmine 7.0.2 and the 7.0 line, in light and dark, at desktop and phone width: no console errors, no failed requests, no sideways scrolling, and text at AA contrast on the pages that matter, including the wiki, the activity page and the Rubylode to-do page.
