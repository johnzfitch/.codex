# Omarchy Manual (Summary)

## Introduction

Omarchy is a polished Arch Linux distribution that uses the tiling compositor **Hyprland**.  It aims to provide a full development environment out of the box with no unnecessary bloat.  The goal is to combine aesthetics and productivity: the desktop, terminal and apps are themed consistently, and the system stays keyboard‑centric so you can work quickly.  Applications such as **Neovim**, **Spotify**, **Chromium**, **Typora**, **Alacritty** and **LibreOffice** are pre‑installed【228908442355530†L24-L35】.

## Installing Omarchy

Omarchy is installed from a bootable ISO.  Use a dedicated drive (dual‑booting requires a second disk) because the installer will wipe the selected drive and enable full‑disk encryption【228908442355530†L53-L60】.  Download the ISO from the official site, write it to a USB stick (Balena Etcher for macOS/Windows or `caligula` on Linux) and boot it【228908442355530†L61-L63】.  Since many PCs ship with **Secure Boot** and **TPM** enabled, these must be disabled in the BIOS【228908442355530†L65-L67】.

## Keyboard‑Driven Navigation

Omarchy is entirely keyboard operated【878633533529002†L14-L18】.  The following hotkeys form the foundation of the system:

- **Launchers and menus** – `Super + Space` opens the application launcher and `Super + Alt + Space` opens the Omarchy menu【878633533529002†L14-L18】.  From there you can access all apps and settings.
- **Starting common apps** – `Super + Return` launches the terminal and `Super + Shift + B` opens the web browser【878633533529002†L20-L24】.  Use `Super + Shift + T` to open the activity monitor and `Super + Shift + F` to start the file manager【878633533529002†L35-L37】.
- **Window management** – Move focus with `Super + Arrow` and swap windows with `Super + Shift + Arrow`【878633533529002†L40-L48】.  Use `Super + J` to toggle between horizontal and vertical tiling【878633533529002†L28-L33】; repeat to toggle back.  `Super + T` toggles a window between tiled and floating【878633533529002†L50-L52】.  `Super + F` makes the window full‑screen, while `Super + Alt + F` makes it full‑width【878633533529002†L53-L54】.  Close the current window with `Super + W`【878633533529002†L50-L52】.
- **Workspaces and groups** – Switch to workspace 1‑4 using `Super + 1/2/3/4` and cycle through workspaces with `Super + Tab` (next) or `Super + Shift + Tab` (previous)【661522998295823†L27-L29】.  Move a window to a workspace with `Shift + Super + number`【661522998295823†L31-L32】.  Group windows together with `Super + G`, cycle through grouped windows with `Super + Alt + Tab` and remove a window from the group with `Super + Alt + G`【878633533529002†L56-L62】.
- **Applications** – Additional hotkeys quickly launch specific programs:  `Super + Shift + F` (file manager), `Super + Shift + T` (activity monitor), `Super + Shift + M` (Spotify), `Super + Shift + N` (Neovim), `Super + Shift + D` (LazyDocker), `Super + Shift + O` (Obsidian) and more【661522998295823†L49-L68】.  Use `Ctrl + Super + S` to open the share menu【661522998295823†L67-L68】.

### Clipboard and Capture

Omarchy provides a universal clipboard: copy with `Super + C`, cut with `Super + X`, paste with `Super + V` and open the clipboard manager with `Super + Ctrl + V`【661522998295823†L74-L83】.  For screenshots, `Print Screen` opens a capture tool with editing, `Shift + Print Screen` copies the screenshot to the clipboard, `Alt + Print Screen` starts/stops screen recording and `Super + Print Screen` opens the color picker【661522998295823†L87-L97】.

### Notifications, Styles and Toggles

Dismiss notifications with `Super + ,` (latest) or `Shift + Super + ,` (all)【661522998295823†L103-L108】.  Toggle Do Not Disturb with `Ctrl + Super + ,`【661522998295823†L103-L109】.  Change themes with `Ctrl + Shift + Super + Space` and cycle background images using `Ctrl + Super + Space`【661522998295823†L113-L121】.  Adjust style transparency with `Super + Backspace`【661522998295823†L116-L118】.  System toggles include preventing sleep (`Ctrl + Super + I`), enabling night light (`Ctrl + Super + N`) and showing/hiding the top bar (`Shift + Super + Space`)【661522998295823†L128-L134】.

### File Manager and Brightness

In the file manager, `Ctrl + L` jumps to a path, the **Space** bar previews files, and **Backspace** moves up one folder【661522998295823†L139-L145】.  For Apple displays, brightness is controlled via `asdcontrol`: `Ctrl + F1` (decrease), `Ctrl + F2` (increase) and `Ctrl + Shift + F2` (maximum)【661522998295823†L148-L154】.

### Neovim (LazyVim) Integration

Omarchy uses a **LazyVim** setup for Neovim.  Press `Space` to open command options, `Space Space` for fuzzy file search, and `Space E` to toggle the file explorer【661522998295823†L160-L167】.  Git commands appear under `Space G G`, while `Space S G` runs a content search【661522998295823†L160-L168】.  Within the sidebar, `A` adds a file, `Shift + A` creates a subdirectory, `D` deletes the selected entry and `R` renames it【661522998295823†L176-L182】.  See LazyVim documentation for a full list of keymaps.

## Themes

Omarchy includes twelve curated themes spanning the terminal, editor, system menu and lock screen【228908442355530†L108-L120】.  Switch themes through *Style > Theme* in the menu or press `Super + Ctrl + Shift + Space`【228908442355530†L110-L116】.  Background images can be rotated with `Super + Ctrl + Space`【228908442355530†L119-L120】.  Additional themes are available from an “extra themes” page, and you can create your own【228908442355530†L122-L123】.

## Other Components

The manual also covers applications (both terminal and GUI), shell tools, shell functions, development tools, web apps, gaming, running a Windows VM, configuration tips, troubleshooting, security and hardware‑specific guides.  For full details, consult the complete manual at the Omarchy website.
