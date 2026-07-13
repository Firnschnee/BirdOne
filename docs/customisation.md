All knobs live at the top of `userChrome.css`:

| Variable | Default | Effect |
|---|---|---|
| `--birdone-tab-share` | `55%` | Share of the row given to the tabs |
| `--birdone-row-height` | `34px` | Height of the combined row |
| `--birdone-tab-inset` | `42px` | Left offset of the tabs (keeps the spaces button clear) |
| `--birdone-accent` | `#fabd2f` | Accent colour replacing the Windows accent |
| `--birdone-accent-text` | `#1a1a1a` | Text on accent surfaces (e.g. the "New Message" button) |

The responsive breakpoint (850px) is hard-coded because media queries
can't read CSS variables. To change it, adjust both `@media (min-width: 850px)`
values in the file.
