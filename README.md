# Veilamp Theme: Dracula

[![license](https://img.shields.io/badge/license-MIT-blue)](LICENSE)

A dark theme for [veilamp](https://gitlab.com/wrewtopia-labs-group/Veilamp) based on the [Dracula](https://draculatheme.com) color palette.

## Dracula Color Palette

The [Dracula specification](https://spec.draculatheme.com) defines a consistent set of colors used across 300+ apps and tools. This theme maps those colors to veilamp's [skin variable system](https://gitlab.com/wrewtopia-labs-group/Veilamp/-/blob/main/docs/EXTENDING.md).

### Base Colors

| Dracula Name | Hex       | Veilamp Variables | Usage |
|--------------|-----------|-------------------|-------|
| Background   | `#282A36` | `--bg-1`, `--app-bg`, `--on-accent` | Mid background shade, window backdrop, text on accent-filled surfaces |
| Current Line | `#44475A` | `--glass`, `::selection` | Translucent glass panel fill, text selection |
| Foreground   | `#F8F8F2` | `--text` | Primary text |
| Comment      | `#6272A4` | `--text-faint`, `--glass-border`, placeholders | Faint labels and captions, panel borders, input placeholder text |

### Accent Colors

| Dracula Name | Hex       | Veilamp Variables | Usage |
|--------------|-----------|-------------------|-------|
| Purple       | `#BD93F9` | `--cyan`, `--accent-grad`, `--glow-cyan`, `--glass-border-bright` | Primary accent, button gradients, neon glow, active panel borders |
| Pink         | `#FF79C6` | `--magenta`, `--accent-grad`, `--glow-magenta` | Secondary accent, gradient end, secondary glow |
| Orange       | `#FFB86C` | `--amber` | VU meters, warm highlights |
| Yellow       | `#F1FA8C` | `--amber-bright` | VU meter peaks |
| Cyan         | `#8BE9FD` | `--cyan` / `--magenta` (variants) | Primary accent in the Cyan variant, secondary in Green |
| Green        | `#50FA7B` | `--cyan` (variant) | Primary accent in the Green variant |

### Derived Colors

Some veilamp variables don't map directly to a Dracula palette color but are derived from them to maintain visual consistency:

| Hex       | Derived From        | Veilamp Variables | Usage |
|-----------|--------------------|--------------------|-------|
| `#21222C` | Background, darker | `--bg-0`, `--app-bg` | Darkest base shade, gradient end of the window backdrop |
| `#343746` | Background, lighter | `--bg-2`, `--glass-strong` | Raised surfaces, headers, modals |
| `#A9B1D6` | Foreground, muted  | `--text-dim` | Secondary / muted text |
| `#7B5FB0` | Purple, muted      | `--cyan-dim` | Dim variant of the primary accent |
| `#B0528A` | Pink, muted        | `--magenta-dim` | Dim variant of the secondary accent |
| `#5AA3B3` | Cyan, muted        | `--cyan-dim` / `--magenta-dim` (variants) | Dim accent in the Cyan and Green variants |
| `#38AD56` | Green, muted       | `--cyan-dim` (variant) | Dim accent in the Green variant |

### Variants

Veilamp themes can ship named variants that layer over the base palette. Pick one from the chips on the theme's card in the palette; the choice is remembered.

| Variant          | Primary Accent | Secondary Accent |
|------------------|----------------|------------------|
| Purple (default) | `#BD93F9` Purple | `#FF79C6` Pink |
| Cyan             | `#8BE9FD` Cyan   | `#BD93F9` Purple |
| Pink             | `#FF79C6` Pink   | `#BD93F9` Purple |
| Green            | `#50FA7B` Green  | `#8BE9FD` Cyan |

Each variant also re-derives the accent gradients, glows, dim accents, and the bright panel border so no element keeps the default purple when another variant is selected. Orange and Yellow stay fixed across all variants.

### Design Decisions

- **Purple as primary**: Dracula's purple (`#BD93F9`) is the most recognizable color in the palette and fills veilamp's `--cyan` slot, which drives the primary accent, button gradients, and neon glow.
- **Dark text on accents**: `--on-accent` is pinned to `#282A36` (Dracula Background) because every Dracula accent is light; veilamp's default white would be unreadable on purple or pink pills.
- **Comment gray for faint UI**: Dracula's Comment color (`#6272A4`) is used for faint captions, panel borders, and input placeholders rather than main interface elements.
- **Glass panels tinted with Current Line**: The translucent `--glass` fill uses `#44475A` at 45% alpha so panels read as Dracula surfaces rather than neutral gray over the backdrop.
- **Orange and Yellow for meters**: veilamp's `--amber` / `--amber-bright` slots map to Dracula Orange and Yellow so VU meters keep a warm look in every variant.
- **Red is unused**: veilamp exposes no error or danger variable, so Dracula Red (`#FF5555`) has no slot in this theme.

## Installation

### As a single file

Open the **Skins** tab, choose **Import theme…**, and select `skin.json`.

### As a skin package

Navigate to **Settings > Appearance > Skin packages > Import folder…** (or **Import .zip…**) and select this repository's folder or a zip of it.

## License

[MIT](LICENSE)
