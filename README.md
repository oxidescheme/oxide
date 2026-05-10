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
<b>oxide</b> is a dark-only colorscheme for your editor and terminal. Deep near-black background, crisp text, and a set of accent colors that stay out of each other's way.
</p>

## Palette

**oxide** uses the OKLCH color space. Instead of eyeballing hex codes and hoping colors look balanced, OKLCH lets us set exact lightness and saturation values.

All accent colors share the same lightness (OKLCH 0.70), so none of them feel louder than the others. They're spaced evenly around the hue wheel and each one maps to a specific UI function — red for errors, blue for variables, green for strings, etc.

See [colors.txt](colors.txt) for the full palette.

## Ports

Ports for the tools we actually use:

* [Neovim](https://github.com/oxidescheme/nvim)
* [Ghostty](https://github.com/oxidescheme/ghostty)
* [VS Code](https://github.com/oxidescheme/vscode)
* [Zellij](https://github.com/oxidescheme/zellij)
* [Antinote](https://github.com/oxidescheme/antinote)

Want oxide in a tool that isn't listed? Use the [template](template/) to create a new port.

## Contributing

PRs welcome. If you're adding a port or fixing a color, make sure it matches the palette in [colors.txt](colors.txt).

## Acknowledgments

* **Oxocarbon**: The spiritual predecessor. oxide borrows heavily from its philosophy of uncompromising contrast.
* **Catppuccin**: For proving that a colorscheme repo can actually be organized. We borrowed their repo structure because it works.

<p align="center">
Copyright &copy; 2025-present oxidescheme
</p>
