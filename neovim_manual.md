# Neovim Manual (Summary)

## About Neovim

**Neovim** is a fork of the popular Vim text editor.  It retains Vim’s modal editing paradigm but modernises the core with asynchronous job control, a built‑in Lua environment and an improved plugin architecture.  The official documentation is divided into two parts:

1. **User manual** – a task‑oriented guide that reads like a book.  It explains how to accomplish editing tasks, from basic to advanced.  The first chapter, “Two manuals,” explains that the user manual should be read sequentially and that the reference manual provides precise descriptions of commands【366215147699181†L24-L33】.
2. **Reference manual** – a precise description of every command and option.  It is structured as hyperlinked help files.  You can jump between topics with `CTRL‑]` and return with `CTRL‑O`【366215147699181†L35-L43】.

To access help inside Neovim, use the `:help` command.  For example, `:help write` displays information about writing files.  The `:helpgrep` command searches across help files【424240676243264†L19-L33】, and `:Tutor` starts an interactive tutorial【366215147699181†L71-L79】.  Customising Neovim begins by creating `init.vim` or `init.lua` in the configuration directory (typically `~/.config/nvim`)【366215147699181†L59-L65】.

## Core Commands and Motions

The quick reference lists hundreds of commands.  Below is a condensed overview of essential motions and editing commands (N indicates an optional count):

| Category | Key/Command | Description |
|-----------------|-------------|------------|
| Move cursor | `h`/`j`/`k`/`l` | Left, down, up, right【976310638817797†L34-L48】 |
| | `0` / `^` / `$` | Beginning of line / first non‑blank / end of line【976310638817797†L38-L43】 |
| | `w`/`W`/`b`/`B` | Move by word / WORD forward/backward【976310638817797†L65-L70】 |
| | `gg` / `G` | Jump to first/last line【976310638817797†L58-L60】 |
| | `/pattern` / `?pattern` | Search forward/backward【976310638817797†L87-L90】 |
| Insert/append | `i` / `a` / `A` | Insert before cursor / append after cursor / append at line end |
| | `o` / `O` | Open new line below/above and enter insert mode |
| Edit | `x` / `dd` / `D` | Delete character / delete line / delete to end of line |
| | `yy` / `p` / `P` | Yank (copy) line / paste after / paste before |
| | `u` / `Ctrl‑r` | Undo / redo |
| Ex commands | `:w` / `:q` / `:wq` / `:qa!` | Write, quit, write and quit, quit all (discard changes) |

For more commands, consult the quick reference page【976310638817797†L17-L31】.

### Windows, Buffers and Tabs

Neovim supports multiple windows (split views), buffers (open files) and tabpages.  Common shortcuts:

- **Splits** – `:split` or `:vsplit` to open horizontal or vertical splits; navigate between splits using `Ctrl‑w` followed by `h`, `j`, `k` or `l`.
- **Buffers** – `:ls` lists open buffers; `:bN` switches to buffer N; `:bd` closes a buffer.
- **Tabs** – `:tabnew` opens a new tab; `gt` cycles through tabs; `:tabclose` closes the current tab.

## Extending Neovim with LazyVim

LazyVim is a curated Neovim distribution that uses the **lazy.nvim** plugin manager.  According to its documentation, LazyVim “transforms Neovim into a full‑fledged IDE” and provides sane defaults for options, autocommands and keymaps【275264860344638†L36-L50】.  Key points:

- **Features** – It ships with a large collection of pre‑configured plugins, enabling LSP support, code completion, fuzzy searching, git integration and more【275264860344638†L46-L51】.
- **Requirements** – Neovim ≥ 0.11.2 built with LuaJIT, Git ≥ 2.19.0, a Nerd Font (optional) and a C compiler for `nvim‑treesitter`【275264860344638†L53-L59】.
- **Getting started** – A starter template is available at `LazyVim/starter`.  To install it: back up your existing `~/.config/nvim` and `~/.local/share/nvim`; clone the starter into `~/.config/nvim`; remove the `.git` directory; then launch Neovim【275264860344638†L79-L96】.  The documentation suggests reading comments in the configuration files to customise your setup.
- **File structure** – LazyVim automatically loads files under `lua/plugins/` and includes default config files that load before your own【275264860344638†L106-L113】.  You can add or override plugin specifications in this directory.

LazyVim provides its own keybindings.  Within Omarchy, some of these are integrated into the system’s hotkeys, such as `Space Space` for fuzzy file search and `Space E` to toggle the sidebar【661522998295823†L160-L167】.

## Learning Resources and License

The Neovim manual is licensed under the Open Publication License【366215147699181†L81-L96】.  For in‑depth learning, run `:Tutor` inside Neovim or explore the online user manual chapters.  A quick reference and index of commands are available on the documentation site【424240676243264†L47-L52】.
