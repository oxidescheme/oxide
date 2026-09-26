# oxide identity

The primary identity is the Open form mark with **Geist Medium (500)** at normal letter spacing. The outlined lockup preserves that exact wordmark without requiring the font to be installed.

| Asset | Use |
| --- | --- |
| `open-form.svg` | Single-color mark on a dark surface |
| `oxide-lockup.svg` | Horizontal mark and wordmark |
| `avatar.svg` | Editable square avatar source with safe padding for circular crops |
| `avatar-1024.png` | Discord, GitHub, and other profile images |
| `social-card.png` | Shared-link preview |

Use `#eeeeee` on `#161616` for the primary mark. Keep accents out of the logo; they are reserved for syntax and meaningful states. The full palette comes from `nvim/lua/oxide/colors.lua`, and UI usage follows `UI_COLOR_GUIDE.md`.

Keep the mark's 64 × 64 viewBox intact so its built-in padding remains consistent. Use `avatar.svg` for square and circular profile images.
