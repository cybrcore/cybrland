![Cybrland banner](./assets/banner.jpg)

# Cybrland
A complete design system and dotfile setup for Hyprland, inspired by cyberpunk aesthetics.

---

## Project Info

> [!CAUTION]
**Status:** Work in progress  
**Current version:** v0.7.5  
**Target stable release:** **v1.0.0 on 2025-12-31**

> [!WARNING]
This project is **not yet stable**.  
Expect breaking changes, missing features, and occasional chaos.  
Please avoid sharing publicly until the 1.0.0 release.

### Related projects
- **[Cybrpapers](https://github.com/scherrer-txt/cybrpapers)** -- hand-crafted cyberpunk wallpapers  
- **[Cybrcolors](https://github.com/scherrer-txt/cybrcolors)** -- unified color palette used across all themes

## Current Status

| Component   | State | Notes |
|------------|--------|-------------------------------|
| Waybar     | 🟢 Done | Stable; fully themed |
| Micro      | 🔵 Beta | Stable; fully themed |
| Kitty      | 🔵 Beta | Stable; fully themed |
| Cava       | 🔵 Beta | Stable; fully themed |
| btop       | 🔵 Beta | Stable; fully themed |
| nvtop      | 🔵 Beta | Stable; fully themed |
| Rofi       | 🔵 Beta | Fully themed; minor refinement needed |
| Hyprland   | 🔵 Beta | Core keybinds, rules, animations |
| Starship   | 🟡 Alpha | Basic prompt; needs refinement |
| Firefox    | 🟡 Alpha | Basic theme; needs refinement |
| VSCode     | 🔴 WIP | Basic theme; early stage |
| yazi       | 🔴 WIP | Basic theme; early stage |
| swaync     | 🔴 WIP | Full theme planned |
| Obsidian   | 🔴 WIP | Plugin-based theme; true standalone theme planned |
| Spicetify  | 🔴 WIP | Full theme planned |
| Vencord    | 🔴 WIP | Full theme planned |
| Emacs/Nvim | 🔴 WIP | Full theme planned |
| Color flavors | 🔴 WIP | Planned feature |

## Roadmap

### v1.0.0 (2025-12-31)
- **Extensive technical documentation**  
  Full breakdown of file structure, color tokens, theme philosophy, overrides, scripts, keybinds, and customization workflow to make the entire setup easy to use and extend for others.
- Finalize Hyprland keybind system; add user guide for creating custom bindings  
- Complete Firefox theme  
- Complete VSCode theme  
- Complete yazi theme  
- Starship production-ready prompt  
- Integration of swaync notification theme  
- Add official color flavors switchable via Waybar or rofi  
- Stabilize all components listed as 🔵 Beta

### v1.5.0 (2026)
- Standalone Obsidian theme (working title: *Cyberian*)  
- Spicetify theme  
- Emacs-Nvim theme
- Vencord theme
- Additional wallpaper bundles (Cybrpapers expansion)

---

# Themes
<div align="left">
  <a href="./waybar/about-waybar.md">
    <img src="assets/waybar.png" height="60" alt="Waybar" />
  </a>
  <a href="./kitty/about-kitty.md">
    <img src="assets/kitty.png" height="60" alt="Kitty" />
  </a>
  <a href="./micro/about-micro.md">
    <img src="assets/micro.png" height="60" alt="Micro" />
  </a>
  <a href="./cava/about-cava.md">
    <img src="assets/cava.png" height="60" alt="Cava" />
  </a>
  <a href="./btop/about-btop.md">
    <img src="assets/btop.png" height="60" alt="btop" />
  </a>
  <a href="./rofi/about-rofi.md">
    <img src="assets/rofi.png" height="60" alt="rofi" />
  </a>
  <a href="./hyprland/about-hyprland.md">
    <img src="assets/hyprland.png" height="60" alt="Hyprland" />
  </a>
  <a href="./starship/about-starship.md">
    <img src="assets/starship.png" height="60" alt="Starship" />
  </a>
  <a href="./firefox/about-firefox.md">
    <img src="assets/firefox.png" height="60" alt="Firefox" />
  </a>
</div>

# Showcase
<p align="left">
  <img src="./assets/inspiration/insp-kitty.png">
</p>
<p align="center">
  <em>Waybar, Hyprland, Kitty, Starship ↗</em>
</p>
<br>
<p align="left">
  <img src="./assets/inspiration/insp-firefox.png">
</p>
<p align="center">
  <em>Firefox ↗</em>
</p>
<br>
<p align="left">
  <img src="./assets/inspiration/insp-btop.png">
</p>
<p align="center">
  <em>btop ↗</em>
</p>
<br>
<p align="left">
  <img src="./assets/inspiration/insp-rofi.png">
</p>
<p align="center">
  <em>rofi ↗ (launcher, clipboard, emoji, powermenu, screenshot menu, wallpaper menu)</em>
</p>
<br>
<p align="left">
  <img src="./assets/inspiration/insp-lock.png">
</p>
<p align="center">
  <em>Hyprlock ↗</em>
</p>

# Prerequisites
- `GeistMono Nerd Font` (download [from here](https://www.nerdfonts.com/font-downloads))
- hwmon (for waybar to display CPU, GPU and RAM)
- [rofi](https://github.com/davatorium/rofi) (launcher)
- [btop](https://github.com/aristocratos/btop) (CPU/RAM/Network resource monitor)
- [nvtop](https://github.com/Syllo/nvtop) (GPU resource monitor)
- [swaync](https://github.com/ErikReider/SwayNotificationCenter) (notifications)
- [topgrade](https://github.com/topgrade-rs/topgrade) (for upgrades)
- [pulseaudio](https://github.com/pulseaudio/pavucontrol) (to control audio)
- [PipeWire](https://archlinux.org/packages/extra/x86_64/pipewire/) (to control audio with keyboard wheel)
- [Sidebery](https://github.com/mbnuqw/sidebery) (vertical tabs extension for Firefox)

# Installation & Pre-flight Guide
Before applying these dotfiles, follow this short pre-flight checklist to avoid configuration conflicts and ensure a smooth setup.

## 1. Backup your existing configs

It’s strongly recommended to back up your current configuration directories:

```sh
mkdir -p ~/.backup_configs
cp -r ~/.config/hypr ~/.backup_configs/hypr 2>/dev/null
cp -r ~/.config/kitty ~/.backup_configs/kitty 2>/dev/null
cp -r ~/.config/waybar ~/.backup_configs/waybar 2>/dev/null
cp -r ~/.config/rofi ~/.backup_configs/rofi 2>/dev/null
cp -r ~/.config/btop ~/.backup_configs/btop 2>/dev/null
```

This allows you to quickly revert if needed.

## 2. Install required dependencies

Make sure the following components are installed:
- Hyprland
- Kitty
- Waybar
- Rofi
- btop
- nvtop
- Nerd Font (GeistMono recommended)
- lm_sensors

On Arch Linux:
```sh
sudo pacman -S rofi-wayland kitty waybar btop nvtop lm_sensors
sudo sensors-detect
```

## 3. Optional: Test in a separate Hyprland profile

You can launch Hyprland with an alternate configuration without touching your main setup:
```sh
cp -r ~/.config/hypr ~/.config/hypr_test
Hyprland --config ~/.config/hypr_test/hyprland.conf
```

Useful for testing without affecting your main environment.

## 4. Check for hardcoded paths

Some paths might need adjustment depending on your system (e.g., wallpapers, scripts).

Run:
```sh
grep -R "~/" cybrland
grep -R "/home" cybrland
grep -R ".local/bin" cybrland
```

Update any paths as needed.

## 5. Review autostart services

These dotfiles may start components such as:
- wallpaper daemon
- idle/lock daemon
- notifications
- clipboard watcher
- Waybar
- Hyprpaper

Check that they don’t conflict with your existing services (e.g., swayidle, ags, systemd user services).

## 6. Commit a snapshot (if using Git-managed dotfiles)

If you version-control your dotfiles:
```sh
git add .
git commit -m "Snapshot before applying cybrland"
```

Makes rollback trivial.

## 7. Revert script (optional, recommended)

Create a simple revert script in case your system doesn’t boot into Hyprland cleanly:
```sh
#!/usr/bin/env bash
mv ~/.config/hypr ~/.config/hypr_bad
cp -r ~/.backup_configs/hypr ~/.config/hypr
```

Save it somewhere accessible (e.g., ~/.local/bin/revert-hypr).

## 8. After installation, test the essentials

Confirm that the following components work correctly:
- Waybar modules (CPU/GPU/network, clock, audio, brightness)
- Rofi launchers
- Kitty theming
- btop theme
- Keybinds (some may differ from your existing setup)
- Wallpaper rotation daemon
- Idle lock functionality
- Hardware monitoring