# BirdOne

One-line layout for Thunderbird: tabs and unified toolbar share a single
row, global search hidden (use CTRL+K).

> Tested on Thunderbird 152 (Supernova UI, 115+ required) on Windows.

![preview](assets/preview.png)

### Features

- Tab bar and unified toolbar merged into one row: tabs on the left,
  toolbar buttons on the right, next to the window controls
- Global search bar hidden – search stays available via **CTRL+K**
- Responsive: below 850px window width the layout falls back to the
  default two-row interface
- Auto-hide aware: if `mail.tabs.autoHide` is enabled and only one tab
  is open, the toolbar keeps its full width instead of leaving an empty
  gap

### Installation

1. Download [`userChrome.css`](https://github.com/Firnschnee/BirdOne/blob/main/userChrome.css)

2. In Thunderbird go to **Settings → General**, scroll to the bottom and
   open **Config Editor**. Search for
   **`toolkit.legacyUserProfileCustomizations.stylesheets`** and set it
   to **`true`**.

3. Recommended: in the same Config Editor set **`mail.tabs.autoHide`**
   to **`false`**, so the tab bar (and with it the one-line layout) is
   always visible, even with a single tab.

4. Find your profile folder: **Help → Troubleshooting Information →
   Profile Folder → Open Folder**.

5. Create a `chrome` folder inside the profile folder if it doesn't
   exist, then copy `userChrome.css` into it.

6. Restart Thunderbird. The layout applies on restart.

### Customisation

All knobs live at the top of `userChrome.css`:

| Variable | Default | Effect |
|---|---|---|
| `--birdone-tab-share` | `55%` | Share of the row given to the tabs |
| `--birdone-row-height` | `34px` | Height of the combined row |
| `--birdone-tab-inset` | `42px` | Left offset of the tabs (keeps the spaces button clear) |

The responsive breakpoint (850px) is hard-coded because media queries
can't read CSS variables. To change it, adjust both `@media (min-width: 850px)`
values in the file.

---
Sibling of [FoxOne](https://github.com/Firnschnee/FoxOne) |
Concept inspired by NeroWolfe_'s one-line experiment | License: [MIT](LICENSE)
