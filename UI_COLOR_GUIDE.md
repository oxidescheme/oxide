# Oxide UI Color Guide

This is the canonical guide for how to apply oxide colors to **UI elements** (borders, selections, status bars, menus, etc.) when creating new ports. Check `nvim/lua/oxide/colors.lua` for palette values and Neovim highlight groups for current roles.

> **For agents**: Read this file before writing any theme files for a new port. Then study at least one existing oxide port to see the principle in practice.

## Philosophy

**Monochrome-first. Accents are for semantic meaning only.**

Oxide's UI should feel like reading text on paper, not like a neon dashboard. The hierarchy comes from lightness contrast (surface/text), not from splashing accent colors on every border, tab, and button.

- **Surface colors** (`mantle`, `base`, `surface0`, `surface1`, `surface2`) create depth and structure
- **Text colors** (`bright_text`, `text`, `subtext0`, `subtext1`, `subtext2`) create information hierarchy
- **Accent colors** (`red`, `orange`, `yellow`, `green`, `teal`, `sky`, `blue`, `purple`, `pink`) are reserved for states that carry meaning: errors, success, warnings, active search, current mode, marked items

If an element does not convey error/success/warning/active-state information, it should use a surface or text color.

## UI Element → Color Mapping

| UI Element | Color | Rationale |
|------------|-------|-----------|
| **App background** | `base` (#161616) | The canvas |
| **Panel background** | `base` or `mantle` | Slightly darker for distinction |
| **Inactive selection bg** | `surface0` (#222222) | Subtle highlight outside the active view |
| **Active selection bg** | `surface1` (#2e2e2e) | One step up for "this is actively selected" |
| **Borders, dividers, lines** | `surface2` (#3a3a3a) | Visible but quiet structural elements |
| **Primary text** | `text` (#cecece) | Default readable text |
| **Bright/emphasized text** | `bright_text` (#eeeeee) | Headings, active labels, important labels |
| **Secondary text** | `subtext0` (#aeaeae) | Descriptions, hints, inactive labels |
| **Muted readable text** | `subtext1` (#808080) | Comments, hints, metadata, disabled items |
| **Quiet chrome** | `subtext2` (#555555) | Line numbers, separators, non-text marks |

## When Accents ARE Appropriate

Use accents **only** for elements that convey specific semantic state. This is the complete list:

| State | Color | Usage |
|-------|-------|-------|
| **Error / critical** | `red` (#ed756e) | Error messages, failed operations, deletion markers, orphan symlinks |
| **Warning / attention** | `orange` (#e48233) or `yellow` (#c39900) | Warnings, search highlights, todo markers, important notifications |
| **Success / added / copied** | `green` (#5bb661) | Success messages, copied files, added items, executables, progress complete |
| **Active search / find** | `yellow` (#c39900) or `blue` (#3ba6f5) | Search keywords, find matches, incremental search highlight |
| **Current mode indicator** | `blue` (#3ba6f5) | The mode you're currently in (normal/insert/visual equivalent) |
| **Marked state** | `teal` (#00baaa) | Marked items and other explicit semantic markers |
| **Keywords / special** | `purple` (#968ff7) | Keywords, static elements, changed items |

**What this means in practice:**
- A tab bar: inactive tabs = `subtext1` on `surface0`, active tab = `bright_text` on `surface1` (monochrome — the position tells you what's active)
- A file manager's selected file: bg = `surface1` (monochrome — the highlight tells you it's selected)
- A file manager's copied file marker: fg/bg = `green` (accent — conveys "this was copied")
- A terminal's active border: fg = `text` or `bright_text` (monochrome — being the active window is structural, not a state)
- A terminal's bell border: fg = `red` (accent — error state)

## What `colors.lua` Comments Mean

The comments in `nvim/lua/oxide/colors.lua` summarize both syntax and editor UI roles. This guide specifies how to carry those roles into other interfaces.

For example:
- `blue = "Properties, info, search, directories"` → This means in **code**, blue colors properties/variables. It does **not** mean "make all UI borders blue."
- `teal = "Preproc, regex, attributes"` → This means in **code**, teal colors preprocessor directives. It does **not** mean "use teal for active pane indicators."

## Examples from Existing Ports

### kitty (`oxide.conf`)
```
active_border_color #cecece       ← text (monochrome — active window is structural)
inactive_border_color #555555     ← subtext2 (monochrome — inactive is structural)
bell_border_color #ed756e         ← red (accent — error state)

active_tab_foreground #cecece     ← text (monochrome)
active_tab_background #2e2e2e     ← surface1 (monochrome)
inactive_tab_foreground #808080   ← subtext1 (monochrome)
```

### nvim (`editor.lua`)
```lua
Visual = { bg = c.surface1 }              ← monochrome active selection
FloatBorder = { fg = c.surface2 }           ← monochrome border
Search = { bg = c.blue, fg = c.base }     ← accent — search is a functional state
ErrorMsg = { fg = c.red }                 ← accent — error is a functional state
```

### Ghostty (`Oxide`)
```
selection-background = #2e2e2e    ← surface1 (monochrome active selection)
```

## Anti-Patterns to Avoid

1. **Don't make all borders an accent color.** Borders are structural. Use `surface2` unless the border specifically indicates an error or active search.
2. **Don't make selected items blue/teal by default.** Active selection = `surface1`; inactive selection = `surface0`. Only use an accent if the selection conveys semantic state (e.g., "this file is copied" = green).
3. **Don't color every tab, button, and label with accents.** Tabs and buttons are structural UI — use the text/surface hierarchy.
4. **Don't copy other colorschemes' UI patterns.** Many colorschemes use accents heavily for borders and chrome. Oxide does not. Look at existing oxide ports, not other themes.
5. **Don't assume "blue = primary accent" for UI.** Blue is for syntax (variables/properties) and specific functional states (search, current mode). It is not oxide's "brand color" for UI decoration.

## Quick Reference

**Monochrome palette for UI chrome:**
- Darkest: `mantle` (#121212) — rare, for deepest background layers
- Background: `base` (#161616) — app background
- Subtle backgrounds: `surface0` (#222222) — cursor line, references, menus
- Active selection: `surface1` (#2e2e2e) — selected text, active items, tabs, popup menus
- Borders: `surface2` (#3a3a3a) — lines, separators, inactive borders

**Text hierarchy:**
- `bright_text` (#eeeeee) — emphasized, active labels
- `text` (#cecece) — primary text
- `subtext0` (#aeaeae) — secondary, descriptions
- `subtext1` (#808080) — comments, hints, metadata, disabled items
- `subtext2` (#555555) — line numbers, separators, non-text marks

**Accent reservation:**
- `red` — errors, deletions, critical
- `orange` / `yellow` — warnings, attention, search
- `green` — success, copied, added, executables
- `teal` — marked state
- `blue` — current mode indicator, active search
- `purple` — keywords, special states
