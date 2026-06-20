# Frosted Glass Custom Theme for Home Assistant

A translucent frosted glass theme for Home Assistant with backdrop-blur effects, Liquid Glass inspired inner bevels, and auto light/dark mode support. User-configurable accent colors via HA's built-in color picker.

![Frosted Glass Light](screenshots/light.png)
![Frosted Glass Dark](screenshots/dark.png)

## Features

- Translucent glass cards with `backdrop-filter: blur()` and inner bevel shadows
- Auto light/dark mode with distinct gradient backgrounds
- Colorful radial gradient backgrounds (no external images needed)
- User-configurable primary and accent colors via HA's Profile settings
- Requires [card-mod](https://github.com/thomasloven/lovelace-card-mod) for glass effects
- Excludes glass from heading cards, glance cards, bubble cards, mushroom title/chips cards
- Two variants: **Full** (with backdrop-blur on cards) and **Lite** (without blur, better performance)

## Variants

| Variant | File | Blur | Performance |
|---------|------|------|-------------|
| **Full** | `frosted_glass_custom.yaml` | Cards, sidebar, dialogs, badges, inputs | Beautiful but heavier on GPU |
| **Lite** | `frosted_glass_custom_lite.yaml` | Sidebar and dialogs only (no card blur) | Lighter, still glass-like |

## Installation

### HACS (recommended)

1. Open HACS in Home Assistant
2. Go to **Frontend** > **3-dot menu** > **Custom repositories**
3. Add `HummelsTech/ha-theme-frosted-glass` as category **Theme**
4. Search for "Frosted Glass Custom" and install
5. Restart Home Assistant
6. Go to **Profile** > **Theme** and select **Frosted Glass Custom** or **Frosted Glass Custom Lite**

### Manual

1. Copy the theme files from `themes/` to your Home Assistant `themes/` directory
2. Make sure your `configuration.yaml` includes:
   ```yaml
   frontend:
     themes: !include_dir_merge_named themes
   ```
3. Restart Home Assistant

## Prerequisites

- [card-mod](https://github.com/thomasloven/lovelace-card-mod) — required for the glass card effects
- Home Assistant 2025.8+ recommended (for primary color scale support)

## Customization

### Accent Colors

The theme does **not** hardcode primary or accent colors. To customize:

1. Go to **Profile** > **Theme** > select **Home Assistant** (default)
2. Choose your **Primary color** and **Accent color**
3. Switch back to **Frosted Glass Custom**
4. Your chosen colors are applied everywhere — sliders, toggles, switches, links

### Backgrounds

The theme uses CSS gradient backgrounds. To use a custom image instead, edit the `background-image` value in the theme file:

```yaml
background-image: "center / cover no-repeat fixed url('/local/backgrounds/your-image.png')"
```

### Card Exclusions

The following card types are excluded from glass effects (no background/blur):
- Heading cards (`hui-heading-card`)
- Glance cards (`hui-glance-card`)
- Mushroom title cards
- Mushroom chips cards (outer container)
- Bubble cards
- Markdown cards with `text-only` class

## Part of the Frosted Glass family

This theme is part of a consistent Frosted Glass look across self-hosted services:

- [*Arr Frosted Glass](https://github.com/HummelsTech/arr-frosted-glass) — Sonarr, Radarr, Prowlarr, Bazarr
- Homarr (Mantine Custom CSS)
- Authentik (login page CSS)
- Nginx Proxy Manager error pages

## Credits

- Inspired by the [Frosted Glass](https://github.com/wessamlauf/homeassistant-frosted-glass-themes) theme by wessamlauf
- Apple Liquid Glass design language
- [card-mod](https://github.com/thomasloven/lovelace-card-mod) by thomasloven

## License

MIT
