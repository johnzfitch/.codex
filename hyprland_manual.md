# Hyprland Manual (Summary)

## Overview

**Hyprland** is a dynamic tiling Wayland compositor written in C++.  It provides various layouts (dwindle, master, etc.), animated window transitions and a flexible configuration system.  The official wiki covers installation, configuration keywords, monitor settings, keybindings (binds), dispatchers and more.

## Installation

Hyprland is actively developed and best supported on Arch Linux and NixOS.  Rolling‑release distributions such as Fedora and openSUSE generally work well, while older or fixed‑release distributions may ship outdated dependencies【210338803522461†L260-L266】.  The project strongly recommends installing Hyprland via your package manager rather than compiling manually【210338803522461†L267-L277】:

- **Arch Linux** – Install the tagged release with `sudo pacman -S hyprland` or use the AUR for the `hyprland-git` package【210338803522461†L291-L299】.  A meta‑package (`hyprland-meta-git`) can be used to pull the latest versions of all hypr‑ ecosystem components【210338803522461†L301-L304】.
- **NixOS** – Enable `programs.hyprland.enable = true;` in your Nix configuration【210338803522461†L311-L317】.
- **openSUSE** – Install via `sudo zypper in hyprland` and optionally install `hyprland-devel` for development【210338803522461†L321-L334】.
- **Fedora** – On Fedora 40+ use `sudo dnf install hyprland` and `sudo dnf install hyprland-devel`【210338803522461†L341-L347】.  For faster updates, the project maintains a Copr repository【210338803522461†L348-L350】.
- **Debian/Ubuntu** – Packages in Debian/Ubuntu are often outdated; if you use these distros it is recommended to build Hyprland manually【210338803522461†L354-L366】.
- **Gentoo** – Install with `emerge --ask gui-wm/hyprland`【210338803522461†L376-L381】.  Additional components are available through the GURU overlay【210338803522461†L382-L391】.

If you encounter “.so file mismatch” errors after compiling from source, the wiki notes that the issue is likely due to mismatched dependencies【210338803522461†L267-L279】.  Use packaged versions to avoid these problems.

## Configuration Basics

Hyprland’s behaviour is defined in a configuration file (typically `~/.config/hypr/hyprland.conf`).  The wiki groups configuration options under categories such as **Variables**, **Keywords**, **Monitors**, **Binds**, **Dispatchers**, **Window Rules**, **Workspace Rules**, **Gestures**, **Animations**, **Environment Variables**, **Multi‑GPU** and more.  Each category has a dedicated documentation page.  A few highlights:

* **Variables** – Define reusable values (e.g. `$mainMod` for the main modifier key) and environment variables.  These can be referenced throughout the config.
* **Monitors** – Configure outputs, resolutions, refresh rates and scaling.  Example: `monitor = HDMI-A-1, 2560x1440@144, 0x0, 1`.
* **Keywords** – Core settings like `general:gaps_in = 4`, `input:kb_layout = us` and `decoration:shadow = yes`.
* **Layouts** – Choose between **dwindle** (similar to i3/sway), **master** (similar to dwm) or others.  Each layout has its own parameters.

## Binds and Keybindings

Keybindings are defined using the `bind` directive:

```
bind = MODS, key, dispatcher, params
```

For example, `bind = SUPER_SHIFT, Q, exec, firefox` opens Firefox when you press **Super + Shift + Q**【981131033055070†L256-L266】.  To bind a key without modifiers, leave the `MODS` field empty (`bind = , Print, exec, grim`)【981131033055070†L270-L272】.  If you need to bind keys by keycode rather than keysym, prefix the key with `code:` (e.g. `bind = SUPER, code:28, exec, amongus`)【981131033055070†L278-L286】.

### Unbinding and Flags

Unbind an existing key with the `unbind` directive, e.g. `unbind = SUPER, O`【981131033055070†L320-L327】.  The key name is case‑sensitive and must match the original bind【981131033055070†L332-L337】.  Binds support optional flags to modify behaviour【981131033055070†L339-L369】:

| Flag | Description |
|------|-------------|
| `l` | Activate even when an input inhibitor (like the lock screen) is active【981131033055070†L351-L352】 |
| `r` | Trigger on release of the key【981131033055070†L351-L355】 |
| `c` | Trigger on release if the mouse cursor stays within a drag threshold【981131033055070†L355-L356】 |
| `g` | Trigger on release if the cursor moves outside the drag threshold (for drags)【981131033055070†L356-L358】 |
| `o` | Trigger on long press【981131033055070†L358-L360】 |
| `e` | Repeat while the key is held【981131033055070†L360-L361】 |
| `n` | Non‑consuming: pass the event through to the active window【981131033055070†L361-L362】 |
| `m` | Bind mouse buttons【981131033055070†L361-L363】 |
| `t` | Transparent: cannot be shadowed by other binds【981131033055070†L363-L364】 |
| `i` | Ignore modifiers【981131033055070†L364-L365】 |
| `s` | Separate: combine multiple keys using `&` (key combos)【981131033055070†L366-L367】 |
| `d` | Add a description for the bind【981131033055070†L367-L368】 |
| `p` | Bypass apps that try to inhibit keybinds【981131033055070†L367-L369】 |

Examples:

- **Volume control** – `binde = , XF86AudioRaiseVolume, exec, wpctl set-volume -l 1.5 @DEFAULT_AUDIO_SINK@ 5%+` repeats while held; `bindl = , XF86AudioLowerVolume, exec, wpctl set-volume @DEFAULT_AUDIO_SINK@ 5%-` works even with the screen locked【981131033055070†L372-L379】.
- **Toggle an application** – `bindr = SUPER, SUPER_L, exec, pkill wofi || wofi` launches or closes *wofi* depending on whether it’s already running【981131033055070†L382-L384】.
- **Long press** – `bindo = SUPER, XF86AudioNext, exec, playerctl next` skips to the next track on long press, while a normal press seeks forward five seconds【981131033055070†L388-L389】.
- **Mouse buttons** – Bind mouse buttons using `mouse:<code>` (e.g. `bind = SUPER, mouse:272, exec, my-command`)【981131033055070†L392-L397】.
- **Combos** – Use the `s` flag and `&` to create multi‑key combos.  For example, `binds = Control_L, A&Z, exec, kitty` binds Ctrl+L with keys A and Z【981131033055070†L409-L416】.

## Further Configuration

Other wiki sections cover dispatchers (actions invoked by keybinds), window and workspace rules, gestures, animations, multi‑GPU setups and performance tuning.  Hyprland also provides a suite of companion tools (hyprpaper, hyprpicker, hypridle, hyprlock, etc.) listed under the **Hypr Ecosystem** section【894672367956411†L54-L68】.  Refer to the wiki for detailed configuration examples and troubleshooting guides.
