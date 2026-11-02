# Contrast

Obsidian is black, white and grey, with colour only for meaning (red, green, amber). It aims at WCAG 2.2 AA in light and dark: 4.5:1 for text (3:1 for large text), and 3:1 for the parts of a control that
identify it (field borders) and for focus indicators.

## How it is measured

- The page check (`npm run check`) loads 29 pages in light and dark, at 1280px and 390px wide, and measures every visible
  piece of text against the colour stacked behind it. On 2026-11-02 against Redmine 7.0.2 with the Rubylode plugins mounted it
  measured 2,942 text pairs per run at desktop width and 3,460 at phone width, in light and in dark, and found none below AA:
  116 of 116 gated runs clean. At the 16px base size every measured pair also reaches 4.5:1, so none relies on the 3:1 allowance for large text.
- The tokens, one pair at a time, below. Field borders and focus rings are not text, so the check does not see them, and it
  skips text over a gradient or an image. Chip colours are the mixes the stylesheet makes (`color-mix`), worked out on each of
  the three row colours a chip can sit on (panel, stripe, hovered row); the lowest is shown.
- The page check runs at 1280px and 390px. The widths between, where the sidebar gives way to the top rows (900px, 1000px, 1099px and 1100px), were loaded in light and dark with the same measurement: 232 runs, no failures and no sideways scrolling.
- The ratios are worked out from the token values in `tokens.css` and `dark.css` with the WCAG relative luminance formula.

## Light

| Pair | Foreground | Background | Ratio |
|---|---|---|---|
| Body text on the page | `#111111` | `#ffffff` | 18.88 |
| Body text on a panel | `#111111` | `#ffffff` | 18.88 |
| Secondary text on the page | `#595959` | `#ffffff` | 7.00 |
| Secondary text on a panel | `#595959` | `#ffffff` | 7.00 |
| Secondary text on a sunken panel or stripe | `#595959` | `#fafafa` | 6.71 |
| Secondary text on a hovered row | `#595959` | `#f0f0f0` | 6.15 |
| Selected sidebar item and view switch | `#000000` | `#ebebeb` | 17.62 |
| Initials on the lightest of their colours (`#1f845a`) | `#ffffff` | `#1f845a` | 4.66 |
| Link on a panel | `#111111` | `#ffffff` | 18.88 |
| Link on a sunken panel or stripe | `#111111` | `#fafafa` | 18.09 |
| Link on a hovered row | `#111111` | `#f0f0f0` | 16.57 |
| White on the primary | `#ffffff` | `#111111` | 18.88 |
| White on the primary, hovered | `#ffffff` | `#333333` | 12.63 |
| Button text | `#2b2b2b` | `#ffffff` | 14.16 |
| Delete button text | `#a3232b` | `#fdecec` | 6.49 |
| Header links | `#2b2b2b` | `#ffffff` | 14.16 |
| Search field text | `#111111` | `#fafafa` | 18.09 |
| Priority Immediate, white on red | `#ffffff` | `#b3123f` | 6.83 |
| Chip New (lowest, on a hovered row) | `#494949` | `#dfdfdf` | 6.76 |
| Chip In Progress (lowest, on a hovered row) | `#825c07` | `#ede4d0` | 4.77 |
| Chip Resolved (lowest, on a hovered row) | `#1c5f40` | `#d5e5dd` | 5.83 |
| Chip Feedback (lowest, on a hovered row) | `#252525` | `#d7d7d7` | 10.65 |
| Chip Closed (lowest, on a hovered row) | `#1c5f40` | `#d5e5dd` | 5.83 |
| Chip Rejected (lowest, on a hovered row) | `#802929` | `#ecd8d8` | 6.78 |
| Chip High (priority) (lowest, on a hovered row) | `#905316` | `#f0e2d3` | 4.81 |
| Chip Urgent (priority) (lowest, on a hovered row) | `#892b2e` | `#eed8d9` | 6.31 |
| Code block (kept light) | `#111111` | `#f5f5f5` | 17.32 |
| Field border on a panel (control) | `#858585` | `#ffffff` | 3.69 |
| Field border on the page (control) | `#858585` | `#ffffff` | 3.69 |
| Header field border (control) | `#858585` | `#ffffff` | 3.69 |
| Focus ring on a panel | `#111111` | `#ffffff` | 18.88 |
| Focus ring on the page | `#111111` | `#ffffff` | 18.88 |

## Dark

| Pair | Foreground | Background | Ratio |
|---|---|---|---|
| Body text on the page | `#f0f0f0` | `#0d0d0d` | 17.05 |
| Body text on a panel | `#f0f0f0` | `#141414` | 16.17 |
| Secondary text on the page | `#a6a6a6` | `#0d0d0d` | 7.98 |
| Secondary text on a panel | `#a6a6a6` | `#141414` | 7.57 |
| Secondary text on a sunken panel or stripe | `#a6a6a6` | `#1a1a1a` | 7.15 |
| Secondary text on a hovered row | `#a6a6a6` | `#222222` | 6.54 |
| Selected sidebar item and view switch | `#ffffff` | `#2a2a2a` | 14.35 |
| Initials on the lightest of their colours (`#1f845a`) | `#ffffff` | `#1f845a` | 4.66 |
| Link on a panel | `#f0f0f0` | `#141414` | 16.17 |
| Link on a sunken panel or stripe | `#f0f0f0` | `#1a1a1a` | 15.27 |
| Link on a hovered row | `#f0f0f0` | `#222222` | 13.96 |
| Black on the primary (white in dark) | `#111111` | `#f0f0f0` | 16.57 |
| Black on the primary, hovered | `#111111` | `#ffffff` | 18.88 |
| Button text | `#dcdcdc` | `#1a1a1a` | 12.69 |
| Delete button text | `#f2a7ae` | `#35202a` | 7.84 |
| Header links | `#c4c4c4` | `#0d0d0d` | 11.14 |
| Search field text | `#f0f0f0` | `#141414` | 16.17 |
| Priority Immediate, white on red | `#ffffff` | `#b3123f` | 6.83 |
| Chip New (lowest, on a hovered row) | `#b6b6b6` | `#323232` | 6.32 |
| Chip In Progress (lowest, on a hovered row) | `#eac779` | `#43381e` | 7.10 |
| Chip Resolved (lowest, on a hovered row) | `#8dcaae` | `#24382f` | 6.66 |
| Chip Feedback (lowest, on a hovered row) | `#d4d4d4` | `#3c3c3c` | 7.44 |
| Chip Closed (lowest, on a hovered row) | `#8dcaae` | `#24382f` | 6.66 |
| Chip Rejected (lowest, on a hovered row) | `#e89999` | `#422828` | 6.03 |
| Chip High (priority) (lowest, on a hovered row) | `#f7bf87` | `#473522` | 7.09 |
| Chip Urgent (priority) (lowest, on a hovered row) | `#f19a9d` | `#45292a` | 6.14 |
| Code block (kept light) | `#111111` | `#f5f5f5` | 17.32 |
| Field border on a panel (control) | `#808080` | `#141414` | 4.66 |
| Field border on the page (control) | `#808080` | `#0d0d0d` | 4.92 |
| Header field border (control) | `#808080` | `#0d0d0d` | 4.92 |
| Focus ring on a panel | `#f0f0f0` | `#141414` | 16.17 |
| Focus ring on the page | `#f0f0f0` | `#0d0d0d` | 17.05 |

## Not covered

- The chip round a date in a list has a decorative border (1.48:1 in light, 2.18:1 in dark). The date itself is text in the row's colour and is measured.
- The initials beside an assignee repeat the name, which stays in the page for screen readers, so the initials are hidden from them.

- Redmine's own avatar colours with white initials: the three that fall below 4.5:1 (red, orange, pink) are darkened; the rest
  are Redmine's.
- Syntax highlighting inside code blocks is Redmine's, made for a light background, which is why code blocks stay light in dark mode.
- Colour is never the only signal: status and priority carry their name in the issue list, and the priority chip its bar count on
  the issue page.
