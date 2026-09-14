---
"@blakfy/accessibility-widget": patch
---

Fix `.info-btn` (the small "i" tooltip icon next to toggle rows and section
labels): color used `--__bg` (the panel's own background color), rendering
as near-invisible text against its own `::before` dot in BOTH themes — dark
text on the dim gray dot in dark mode, and the mirror-image failure in light
mode. Switched to `--__text`, the theme's actual foreground color, which
contrasts correctly against the dot in both directions.
