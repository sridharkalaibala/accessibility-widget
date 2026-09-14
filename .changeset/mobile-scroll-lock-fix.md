---
"@blakfy/accessibility-widget": patch
---

Fix background page scrolling behind the open panel on touch devices.
`overflow:hidden` on `<html>` alone does not stop touch-driven background
scroll on iOS/Android (the page still pans under the finger). Dialog now
pins `<body>` with `position: fixed` at the current scroll offset while
open, restoring it on close. Also added `overscroll-behavior: contain` to
the panel so it can't scroll-chain into the page once its own content
reaches the top/bottom. Verified with a real CDP touch-drag gesture: panel
scrollTop moved, page scrollY stayed at 0.
