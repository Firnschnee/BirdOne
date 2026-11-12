---
layout: default
title: Customisation
---

# Customisation

All knobs live at the top of `userChrome.css`:

| Variable | Default | Effect |
|---|---|---|
| `--birdone-tab-share` | `55%` | Share of the row given to the tabs |
| `--birdone-row-height` | `34px` | Height of the combined row |
| `--birdone-tab-inset` | `42px` | Left offset of the tabs (keeps the spaces button clear) |
| `--birdone-accent` | `#fabd2f` | Accent colour, replaces the Windows accent (selection, primary buttons, focus rings, active tab line) |
| `--birdone-accent-text` | `#282828` | Text on accent surfaces |
| `--birdone-folder-icon` | `#1e180a` | One colour for all folder icons in the folder pane, instead of Thunderbird's colour per folder type. The icons only show on hovered and selected rows, where the dark amber sits on the row like an imprint |
| `--birdone-titlebar` | `#202020` | Grey of the message list header bar in dark mode |
| `--birdone-attachment-height` | `160px` | Height cap of the attachment panel above the message body (`none` removes the cap) |

Block 15 hides the folder icons until a row is hovered or selected. Account,
tag, busy and error icons always stay visible. To see all folder icons all the
time, comment out the last rule of the block and pick a lighter
`--birdone-folder-icon`, because the dark default nearly disappears on the
plain folder pane.

Block 12 moves the attachment panel above the message body. Set
`mailnews.attachments.display.start_expanded` to `true` in the config editor
(Settings > General > Config Editor) to have the panel open by default. If you
don't want the panel moved at all, comment the block out.

The responsive breakpoint (850px) is hard-coded because media queries
can't read CSS variables. To change it, adjust both `@media (min-width: 850px)`
values in the file.

## Palette

The greys are not variables but a token swap: block 4 of `userChrome.css`
replaces Thunderbird's own dark greys (`--color-gray-40` to `-90` and the
`--color-surface-*-dark` family), and every surface built on them follows.
FoxOne's base `#282828` takes the place of Thunderbird's `#27272a`, and every
other grey keeps its lightness ratio to it, so the hierarchy stays the one
Thunderbird draws. The block lists the native and the new values side by side.

To retheme, change the values in block 4 and the same values in
`userContent.css` (block 1). Content documents can't read variables from
`userChrome.css`, so both files carry their own copy. The accent in
`userContent.css` (block 2) is a hex copy for the same reason.

The palette only applies in dark mode. In light mode Thunderbird uses the same
tokens for text colours, so BirdOne leaves them alone and only the amber accent
remains.
