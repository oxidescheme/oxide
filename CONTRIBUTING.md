# Contributing to Oxide

First off, thank you for considering contributing to Oxide! This ecosystem relies on community contributions to bring the colorscheme to new tools, editors, and websites.

## Philosophy

Before contributing, please keep our core philosophy in mind:
- **Dark-only**: Oxide is a dark-only colorscheme. Do NOT suggest, document, or implement light mode.
- **Function First**: Visual silence, calculated colors, and a minimalist approach.

## Source of Truth for Colors

The **canonical source of truth** for all Oxide colors is the Neovim port.
When adding a new port or updating colors, **always** source your hex or OKLCH values from:
[`nvim/lua/oxide/colors.lua`](https://github.com/oxidescheme/nvim/blob/main/lua/oxide/colors.lua)

Do NOT copy colors from other ports, as they may be outdated or use different formats.

## How to Contribute

### 1. Creating a New Port
Don't see your favorite editor or terminal? You can create a new port!
1. Start with the [oxide template repository](https://github.com/oxidescheme/template).
2. Follow the instructions in `TEMPLATE_GUIDE.md`.
3. Create the port using the canonical colors.
4. Open an issue to let us know, and we can help bring the repository into the `@oxidescheme` organization.

### 2. Creating a Userstyle
Want to bring Oxide to a specific website?
1. Go to the [userstyles repository](https://github.com/oxidescheme/userstyles).
2. Follow the instructions in its README to add a new website to the collection.

### 3. Fixing Bugs or Improving Existing Ports
Found a typo, a missing highlight group, or a visual bug?
1. Find the specific port repository (e.g., `github.com/oxidescheme/alacritty`).
2. Fork the repository and create a branch (`git checkout -b fix-xyz`).
3. Make your changes and test them.
4. Submit a Pull Request.

## Finding Something to Do
Look for issues tagged with `good first issue` or `help wanted` across our repositories. These are specifically scoped out to be approachable for new contributors.
