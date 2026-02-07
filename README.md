<div align="center">

# oxide

</div>

<h6 align="center">
Where function meets form.
</h6>

<p align="center">
  <a href="https://github.com/oxidescheme/oxide/stargazers"><img src="https://img.shields.io/github/stars/oxidescheme/oxide?colorA=161616&colorB=00a6ff&style=for-the-badge"></a>
  <a href="https://github.com/oxidescheme/oxide/issues"><img src="https://img.shields.io/github/issues/oxidescheme/oxide?colorA=161616&colorB=ff5655&style=for-the-badge"></a>
  <a href="https://discord.gg/p8GcbBH5MR"><img src="https://img.shields.io/discord/1450777325267456097?style=for-the-badge&color=00baaa&labelColor=161616&logo=discord&logoColor=white"></a>
</p>

<p>
<b>oxide</b> is a colorscheme that bridges functionality with minimalist aesthetics.
It is built around clarity and restraint, using a deep near-black background, crisp white foregrounds, and vibrant accent colors to emphasize structure without visual noise.

oxide is designed with the same principles of balance and readability, using a deep near-black background that adapts well to different environments without changing its character.
</p>

## Design Philosophy

**oxide** is built on three core principles:

* **Function first**: Every color exists to convey information
* **Visual silence**: Elegance emerges from what is intentionally omitted
* **Systematic harmony**: Every color relates predictably to the others

### Palette

**oxide** uses OKLCH color space instead of guessing hex codes. OKLCH (Lightness Chroma Hue) is a color space that matches how humans actually see color, letting us set precise lightness and saturation values so colors look balanced and don't clash.

The palette is built around three key principles:

* **Perceptual uniformity**: All accent colors share identical lightness values (OKLCH 0.70), ensuring they feel equally prominent to the human eye
* **Semantic consistency**: Each color serves a specific functional purpose—red for errors, blue for variables, green for success states
* **Mathematical harmony**: Colors are positioned at precise intervals around the hue wheel, creating natural visual relationships

**Core Structure:**

* **Background**: Deep void-like `#161616` (OKLCH 0.20) optimized for long coding sessions
* **Foreground**: Crisp text hierarchy from bright white `#dedede` down to subtle `#484848`
* **Accent System**: 9 semantic colors at consistent lightness, each mapped to specific UI functions
* **Terminal Colors**: 16-color ANSI palette with bright variants for maximum compatibility

## Ports

We are currently focused on the tools that matter.

<details open>
<summary>Editors & Terminals</summary>

* [Neovim](https://www.google.com/search?q=https://github.com/oxidescheme/oxide.nvim)
* [Ghostty](https://www.google.com/search?q=https://github.com/oxidescheme/ghostty)

</details>

## Contributing

Minimalism doesn't mean stagnation. If you want to port oxide to a new tool, ensure you strip away the excess before submitting. We like PRs that delete more lines than they add.

## Gratitude

This project stands on the shoulders of giants (and very organized people).

* **Oxocarbon**: The spiritual predecessor. It was my favorite scheme, and oxide borrows heavily from its philosophy of uncompromising contrast.
* **Catppuccin**: For proving that a colorscheme repo can actually be organized. We stole their repo structure because it works.

<p align="center">
Copyright &copy; 2025-present oxidescheme
</p>
