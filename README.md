# Glassy Bar

<img width="1080" height="608" alt="screenshot-2026-10-28_12-45-19" src="https://github.com/user-attachments/assets/de0d6daa-04dc-465a-9c7d-64147fc71c54" />

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

## Screenshots

<img width="1080" height="608" alt="screenshot-2026-10-28_13-50-07" src="https://github.com/user-attachments/assets/44d38776-7367-4486-bdba-05c5a5389ede" />
<img width="1080" height="608" alt="screenshot-2026-10-28_13-42-13" src="https://github.com/user-attachments/assets/535f5eb8-43ac-455f-9376-5bc85dbd3428" />
<img width="1080" height="608" alt="screenshot-2026-10-28_13-04-24" src="https://github.com/user-attachments/assets/e51f4346-bd5a-42a0-889c-c34eba560ec9" />
<img width="1080" height="608" alt="screenshot-2026-10-28_12-50-04" src="https://github.com/user-attachments/assets/c0edb0d4-aa7d-4ee6-b495-7c8b1bd28ad9" />
<img width="1080" height="608" alt="screenshot-2026-10-28_12-47-20" src="https://github.com/user-attachments/assets/f7ec4bf6-a7a3-4ca9-a3db-bb7ce017fd55" />
<img width="1080" height="608" alt="screenshot-2026-10-28_12-46-54" src="https://github.com/user-attachments/assets/2fe534c6-3945-4ab9-a52e-c936005cf819" />
<img width="1080" height="608" alt="screenshot-2026-10-28_12-46-07" src="https://github.com/user-attachments/assets/07acf9b9-655a-4f69-ac00-18dca318699c" />
<img width="1080" height="608" alt="screenshot-2026-10-28_12-43-52" src="https://github.com/user-attachments/assets/92d76694-3e7a-4836-b3a0-99f8efac81b7" />
<img width="1080" height="608" alt="screenshot-2026-10-28_12-43-20" src="https://github.com/user-attachments/assets/889c8719-b302-43b1-8628-8b52ca3ba4ba" />
