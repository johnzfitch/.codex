# Omarchy Environment – Agent Knowledge Base

This directory contains documentation and guides required for managing the Omarchy workstation.  The **ChatGPT CLI** uses these markdown files as its knowledge base.  All manuals live under `./docs/`, and this file indexes them for easy access.

## File Structure

```
.codex/
├── agents.md        ← this index
└── docs/
    ├── omarchy_manual.md    ← summary of the Omarchy manual
    ├── neovim_manual.md     ← summary of the Neovim/Vis manual and LazyVim notes
    └── hyprland_manual.md   ← summary of the Hyprland wiki
```

Place any future documentation inside the `docs/` directory and update this index with a brief description and link.

## Knowledge Base

- **Omarchy Manual** – see [`docs/omarchy_manual.md`](docs/omarchy_manual.md) for an overview of the Omarchy distribution.  It explains installation, navigation, hotkeys, themes, LazyVim integration and other core concepts gleaned from the official manual.
- **Neovim Manual** – [`docs/neovim_manual.md`](docs/neovim_manual.md) summarises the Neovim user and reference manuals.  It provides a quick reference for essential motions and commands, outlines how to access built‑in help, and describes the LazyVim distribution used in Omarchy.
- **Hyprland Manual** – [`docs/hyprland_manual.md`](docs/hyprland_manual.md) summarises the official Hyprland wiki.  It covers package installation for various distributions, explains how to define keybindings (`bind` and `unbind`), lists available bind flags and provides context about other configuration categories.

## Usage

When writing agent actions or responding to user commands related to Omarchy, Hyprland or Neovim, reference the appropriate manual summary.  For deeper details that are not captured in these summaries, consult the official upstream documentation via the links cited in the markdown files.
