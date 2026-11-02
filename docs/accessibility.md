# Contrast

Obsidian aims at WCAG 2.2 AA in light and dark: 4.5:1 for text (3:1 for large text), and 3:1 for the parts of a control that
identify it (field borders) and for focus indicators.

## How it is measured

- The page check (`npm run check`) loads 29 pages in light and dark, at 1280px and 390px wide, and measures every visible
  piece of text against the colour stacked behind it. On 2026-11-02 against Redmine 7.0.2 with the Rubylode plugins mounted it
  measured 3,267 text pairs per run at desktop width and 3,392 at phone width, in light and in dark, and found none below AA:
  116 of 116 gated runs clean.
- The tokens, one pair at a time, below. Field borders and focus rings are not text, so the check does not see them, and it
  skips text over a gradient or an image. Chip colours are the mixes the stylesheet makes (`color-mix`), worked out on each of
  the three row colours a chip can sit on (panel, stripe, hovered row); the lowest is shown.
- The ratios are worked out from the token values in `tokens.css` and `dark.css` with the WCAG relative luminance formula.

## Light

| Pair | Foreground | Background | Ratio |
|---|---|---|---|
| Body text on the page | `#14161c` | `#ffffff` | 18.08 |
| Body text on a panel | `#14161c` | `#ffffff` | 18.08 |
| Secondary text on the page | `#565c6d` | `#ffffff` | 6.67 |
| Secondary text on a panel | `#565c6d` | `#ffffff` | 6.67 |
| Secondary text on a sunken panel or stripe | `#565c6d` | `#fafafb` | 6.40 |
| Secondary text on a hovered row | `#565c6d` | `#eef2ff` | 5.97 |
| Link on a panel | `#2f5ee0` | `#ffffff` | 5.53 |
| Link on a sunken panel or stripe | `#2f5ee0` | `#fafafb` | 5.30 |
| Link on a hovered row | `#2f5ee0` | `#eef2ff` | 4.94 |
| White on the primary | `#ffffff` | `#2f5ee0` | 5.53 |
| White on the primary, hovered | `#ffffff` | `#254bb8` | 7.56 |
| Button text | `#2c303d` | `#ffffff` | 13.15 |
| Delete button text | `#a3232b` | `#fdecec` | 6.49 |
| Header links | `#2c303d` | `#ffffff` | 13.15 |
| Search field text | `#14161c` | `#fafafb` | 17.34 |
| Priority Immediate, white on red | `#ffffff` | `#b3123f` | 6.83 |
| Chip New (lowest, on a hovered row) | `#1c3886` | `#d3ddfb` | 7.91 |
| Chip In Progress (lowest, on a hovered row) | `#825c07` | `#ebe6dd` | 4.85 |
| Chip Resolved (lowest, on a hovered row) | `#1c5f40` | `#d3e6ea` | 5.90 |
| Chip Feedback (lowest, on a hovered row) | `#533794` | `#e0ddfe` | 6.81 |
| Chip Closed (lowest, on a hovered row) | `#404450` | `#dce0ee` | 7.38 |
| Chip Rejected (lowest, on a hovered row) | `#802929` | `#ebdae5` | 6.92 |
| Chip High (priority) (lowest, on a hovered row) | `#905316` | `#eee3e0` | 4.86 |
| Chip Urgent (priority) (lowest, on a hovered row) | `#892b2e` | `#eddae6` | 6.44 |
| Code block (kept light) | `#14161c` | `#f4f5f7` | 16.58 |
| Field border on a panel (control) | `#868b9b` | `#ffffff` | 3.40 |
| Field border on the page (control) | `#868b9b` | `#ffffff` | 3.40 |
| Header field border (control) | `#868b9b` | `#ffffff` | 3.40 |
| Focus ring on a panel | `#3f76ff` | `#ffffff` | 4.00 |
| Focus ring on the page | `#3f76ff` | `#ffffff` | 4.00 |

## Dark

| Pair | Foreground | Background | Ratio |
|---|---|---|---|
| Body text on the page | `#eceef4` | `#0f1115` | 16.29 |
| Body text on a panel | `#eceef4` | `#14161b` | 15.60 |
| Secondary text on the page | `#a2a8b9` | `#0f1115` | 7.95 |
| Secondary text on a panel | `#a2a8b9` | `#14161b` | 7.62 |
| Secondary text on a sunken panel or stripe | `#a2a8b9` | `#191c22` | 7.18 |
| Secondary text on a hovered row | `#a2a8b9` | `#172145` | 6.60 |
| Link on a panel | `#7f9bff` | `#14161b` | 6.92 |
| Link on a sunken panel or stripe | `#7f9bff` | `#191c22` | 6.53 |
| Link on a hovered row | `#7f9bff` | `#172145` | 6.00 |
| White on the primary | `#ffffff` | `#2f5ee0` | 5.53 |
| White on the primary, hovered | `#ffffff` | `#254bb8` | 7.56 |
| Button text | `#d6dae4` | `#191c22` | 12.20 |
| Delete button text | `#f2a7ae` | `#35202a` | 7.84 |
| Header links | `#bcc1cf` | `#0f1115` | 10.50 |
| Search field text | `#eceef4` | `#14161b` | 15.60 |
| Priority Immediate, white on red | `#ffffff` | `#b3123f` | 6.83 |
| Chip New (lowest, on a hovered row) | `#8da6ee` | `#1b2c61` | 5.59 |
| Chip In Progress (lowest, on a hovered row) | `#eac779` | `#3a373b` | 7.23 |
| Chip Resolved (lowest, on a hovered row) | `#8dcaae` | `#1b384c` | 6.52 |
| Chip Feedback (lowest, on a hovered row) | `#bfa5fa` | `#2c2c65` | 6.03 |
| Chip Closed (lowest, on a hovered row) | `#aeb1bc` | `#262f51` | 6.10 |
| Chip Rejected (lowest, on a hovered row) | `#e89999` | `#392745` | 6.09 |
| Chip High (priority) (lowest, on a hovered row) | `#f7bf87` | `#3e343f` | 7.22 |
| Chip Urgent (priority) (lowest, on a hovered row) | `#f19a9d` | `#3c2846` | 6.22 |
| Code block (kept light) | `#14161c` | `#f4f5f7` | 16.58 |
| Field border on a panel (control) | `#7a8094` | `#14161b` | 4.60 |
| Field border on the page (control) | `#7a8094` | `#0f1115` | 4.81 |
| Header field border (control) | `#7a8094` | `#0f1115` | 4.81 |
| Focus ring on a panel | `#7f9bff` | `#14161b` | 6.92 |
| Focus ring on the page | `#7f9bff` | `#0f1115` | 7.23 |

## Not covered

- Redmine's own avatar colours with white initials: the three that fall below 4.5:1 (red, orange, pink) are darkened; the rest
  are Redmine's.
- Syntax highlighting inside code blocks is Redmine's, made for a light background, which is why code blocks stay light in dark mode.
- Colour is never the only signal: status and priority carry their name in the issue list, and the priority chip its bar count on
  the issue page.
