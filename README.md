# Glassy Bar

A floating, see-through pill bar for Omarchy with a soft inner shadow that
takes its colors from your theme.

It's a fork of the stock Omarchy bar, so your widgets, layout, and bar
commands work exactly the same. Only the look changes.

## Install

```sh
omarchy plugin add https://github.com/imdevan/glassy.bar --enable
```

## Configure

Create `~/.config/glassy.bar/config.json`:

Copy from plugin example (after install):
```bash
mkdir $HOME/.config/glassy.bar && cp $HOME/.config/omarchy/plugins/glassy.bar/config.json $HOME/.config/glassy.bar
```

```jsonc
{
  "position": "bottom",                  // top, bottom, left, right
  "width": "full",                       // "full", pixels (1200), or "80%"
  "margin": { "edge": 8, "sides": 8 },   // gap to the screen edges
  "padding": 8,                          // space inside the pill's ends
  "radius": "pill",                      // "pill" or pixels (0 = square)
  "opacity": 0,                          // 0 = clear glass, 1 = solid
  "blur": false,                         // frost what's behind the bar
  "split": false,                        // one pill per section instead of one bar
  "background": "",                      // "" = theme, "#1e1e2e", or "accent"
  "foreground": "",                      // "" = theme, "#cdd6f4", or "accent"
  "border": { "width": 1, "opacity": 0.3 },
  "shadow": { "depth": 10, "opacity": 0.9, "tint": 0.22 }
}
```

Save the file and the bar updates right away.

| Key | What it does |
|-----|--------------|
| `position` | Which screen edge the bar sits on. `""` lets you drag the bar instead. |
| `width` | How long the bar is. Anything short of `"full"` is centered. |
| `margin.edge` | Gap between the bar and the screen edge it sits on. |
| `margin.sides` | Smallest gap to the other two edges. |
| `padding` | Space between the pill's ends and the first/last widget. |
| `radius` | Corner roundness. |
| `opacity` | How solid the background is. |
| `background` | Optional fill color, shown at `opacity`. |
| `foreground` | Optional color for all bar text and icons. Overrides the wallpaper-matched text color. |
| `blur` | Blurs whatever is behind the bar. Strength comes from Hyprland's `decoration.blur` settings, which must be enabled. Hyprland only blurs pixels that aren't fully clear, so with blur on, `opacity` is at least `0.01`. |
| `split` | Gives the left, center, and right sections their own pill (fill, border, shadow, blur) and leaves the space between them clear, so the bar reads as separate floating pieces. `padding` becomes the space inside each section's pill. Empty sections draw nothing. |
| `border` | Thin accent-colored outline. `width: 0` hides it. |
| `shadow.depth` | How far the inner shadow reaches, in pixels. |
| `shadow.opacity` | How dark the shadow is. |
| `shadow.tint` | How much of your theme's accent color is mixed in (0 to 1). |

### Colors

- **Colors** take `"#rgb"`, `"#rrggbb"`, `"#aarrggbb"`, or a theme color name:
  `background`, `foreground`, `accent`, `muted`, `urgent`. Leave them `""` to
  follow your theme.



## Remove

```bash
omachy plugin remove glassy.bar && rm -rf $HOME/.config/glassy.bar
```
