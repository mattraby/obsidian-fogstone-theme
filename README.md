# Fogstone

A soft, eye-friendly Obsidian theme inspired by the Base16 Flat palette. Fogstone pairs muted fog-gray surfaces with desaturated accents for comfortable long-form reading in both dark and light modes. The name comes from those surfaces: fog-gray in light mode, stone-gray in dark mode.

## Design philosophy

**Soft over saturated.** The original Flat UI palette (`flatuicolors.com`) was designed for UI elements — buttons, badges, status bars — where colors appear in small, punchy doses. Fogstone takes the same hue identities but desaturates them (~40% saturation, ~65-70% lightness) so they can be used for body text, headings, and syntax highlighting without straining the eye during long reading sessions.

**Hierarchy through color AND saturation.** Primary headings (H1, H2, H3) get cool accents (dusty blue, lavender, muted teal). Deeper headings (H4, H5, H6) fade to progressively muted grays. This communicates hierarchy through both size and color weight, rather than relying on size alone.

**Warm peach emphasis.** Bold text uses a soft peach (`#D7A77E`) rather than the conventional red — warm and emphatic without triggering the "error/alert" association that bright red creates when used repeatedly in lists and inline prose.

**Fog-gray light mode.** The light mode background is a soft gray (`#E6E9EC`) rather than near-white. Lower overall contrast means borders can also be lighter (`#CED2D6`), resulting in a calmer, more paper-like reading experience.

## Palette

### Grayscale (shared)

| Token | Hex | Use |
|-------|-----|-----|
| `--flat-wet-asphalt` | `#2C3E50` | Dark mode primary background |
| `--flat-midnight` | `#34495E` | Dark mode secondary background |
| `--flat-asbestos` | `#7F8C8D` | Muted gray, light mode body text |
| `--flat-concrete` | `#95A5A6` | Comments, italic text |
| `--flat-silver` | `#BDC3C7` | Faint foreground |
| `--flat-gray` | `#e0e0e0` | Default foreground (dark mode, original) |
| `--flat-soft-text` | `#D0D4D8` | Soft body text (dark mode) |

### Fog (light mode backgrounds)

| Token | Hex | Use |
|-------|-----|-----|
| `--flat-fog` | `#E6E9EC` | Primary background |
| `--flat-fog-alt` | `#DFE2E5` | Sidebar, panels, code blocks |
| `--flat-fog-deep` | `#D7DADD` | Active/hover states |
| `--flat-mist` | `#CED2D6` | Subtle borders |
| `--flat-mist-hover` | `#B8BCC0` | Borders on hover |

### Accents — bright (UI chrome only)

These are the original Flat UI colors. Use them only for UI chrome (focus rings, callout icons, status bar) where saturation is fine.

| Token | Hex | Name |
|-------|-----|------|
| `--flat-alizarin` | `#E74C3C` | Red |
| `--flat-carrot` | `#E67E22` | Orange |
| `--flat-sunflower` | `#F1C40F` | Yellow |
| `--flat-emerald` | `#2ECC71` | Green |
| `--flat-turquoise` | `#1ABC9C` | Cyan |
| `--flat-peter-river` | `#3498DB` | Blue |
| `--flat-amethyst` | `#9B59B6` | Purple |

### Accents — soft (text-facing)

Desaturated versions of each Flat accent. Use these for headings, bold text, inline code, links, syntax highlighting.

| Token | Hex | Name |
|-------|-----|------|
| `--flat-soft-red` | `#D49486` | Soft coral |
| `--flat-soft-orange` | `#D7A77E` | Warm peach |
| `--flat-soft-yellow` | `#D9C779` | Muted gold |
| `--flat-soft-green` | `#8FBE9C` | Sage |
| `--flat-soft-cyan` | `#7BBCAE` | Muted teal |
| `--flat-soft-blue` | `#85ABD0` | Dusty blue |
| `--flat-soft-purple` | `#AE93C2` | Lavender |

### Light mode darker variants

For light mode, the soft accents need slightly darker versions to maintain adequate contrast on a light background.

| Soft color | Dark mode (`#65-70% L`) | Light mode (`#45-50% L`) |
|-----------|------------------------|--------------------------|
| Coral | `#D49486` | `#B07066` |
| Peach | `#D7A77E` | `#B8875F` |
| Gold | `#D9C779` | `#B09A4C` |
| Sage | `#8FBE9C` | `#5C9E73` |
| Teal | `#7BBCAE` | `#5A9E90` |
| Blue | `#85ABD0` | `#5A8BB5` |
| Lavender | `#AE93C2` | `#8B6FA6` |

## Element mapping

### Headings

| Level | Dark mode | Light mode |
|-------|-----------|------------|
| H1 | Dusty blue `#85ABD0` | Darker blue `#5A8BB5` |
| H2 | Lavender `#AE93C2` | Darker lavender `#8B6FA6` |
| H3 | Muted teal `#7BBCAE` | Darker teal `#5A9E90` |
| H4 | Silver (muted) | Concrete (muted) |
| H5 | Concrete (more muted) | Asbestos (more muted) |
| H6 | Asbestos (most muted) | `#5D6D7E` (most muted) |

### Text emphasis

| Element | Dark mode | Light mode |
|---------|-----------|------------|
| Body text | `#D0D4D8` | Asbestos `#7F8C8D` |
| **Bold** | Soft peach `#D7A77E` | Darker peach `#B8875F` |
| *Italic* | Concrete gray `#95A5A6` | Concrete gray |

### Code

Inline code stays uniform (soft teal). Code blocks get per-token syntax highlighting:

| Role | Dark / Light |
|------|--------------|
| Comment | Concrete gray (italic) |
| Keyword | Lavender / darker lavender |
| String | Sage / darker sage |
| Number, boolean, constant | Peach / darker peach |
| Function, class, property | Dusty blue / darker dusty blue |
| Tag, variable, regex | Coral / darker coral |
| Important | Gold / darker gold |
| Operator, punctuation | Soft text / asbestos |

## Installation

Drop the `Fogstone` folder into your vault's `.obsidian/themes/` directory, then activate it via **Settings → Appearance → Themes → Fogstone**.

```shell
# Example: copy Fogstone to another vault
cp -r "/path/to/source/.obsidian/themes/Fogstone" "/path/to/target/.obsidian/themes/"
```

## Customization

All color values live in the `:root` block at the top of `theme.css`. To tweak the palette, change values there and all downstream usages will update automatically. The theme is organized by section:

1. `:root` — base + soft palette definitions
2. `.theme-dark` — dark mode variable bindings
3. `.theme-light` — light mode variable bindings
4. Prism syntax highlighting rules (reading view)
5. CodeMirror 6 syntax highlighting rules (edit view)
6. Inline code, bold, italic, blockquote polish

## Credits

- **Palette origins**: [Flat UI Colors](https://flatuicolors.com) by Designmodo
- **Base16 heritage**: The Base16 framework by Chris Kempson
- **VS Code inspiration**: [Base16 Flat Dark](https://marketplace.visualstudio.com/items?itemName=andrsdc.base16-themes) by andrsdc

## License

MIT
