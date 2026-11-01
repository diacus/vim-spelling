# vim-spelling

Spell checking helpers for the Vim editor, by [@diacus](https://github.com/diacus).

Mappings to turn spell checking on and off quickly, and to correct words
flagged as misspelled through insert-mode completion. The plugin is written
in legacy Vimscript, defines no commands and no global variables — only two
mappings and their autoload helpers.

## Features

- **Toggle spell checking** with a single key (`<F2>`).
- **Fix misspelled words** from a suggestions menu, both in normal and
  insert mode.
- **Non-invasive highlighting**: while spell checking is on, `cursorline`
  is disabled and syntax highlighting is turned off, so the squiggly marks
  over misspelled words are easy to see. Everything is restored when
  spell checking is turned off again.
- **`<Tab>` suggestions**: while spell checking is active, `<Tab>` — in
  both normal and insert mode — opens a completion menu with the spelling
  suggestions for the word under or before the cursor; `<Tab>` is unmapped
  and restored when spell checking is off. (This means the usual insert
  mode expansion is unavailable while the check is on.)

## Installation

### vim-plug

Add the following line to your `vimrc` inside the plug section:

```vim
call plug#begin()
" ...
Plug 'diacus/vim-spelling'
" ...
call plug#end()
```

Then run `:PlugInstall` (or restart Vim).

### Manual

Copy the plugin directories into your `~/.vim` directory (or use any
plugin manager of your preference):

```sh
git clone https://github.com/diacus/vim-spelling.git
cp -r vim-spelling/{plugin,autoload,doc} ~/.vim/
```

## Usage

| Mapping | Mode | Action |
| ------- | ---- | ------ |
| `<F2>` | Normal | Toggles spell checking on/off |
| `<Leader><Space>` | Normal | Shows the spelling suggestions for the word before the cursor |
| `<Tab>` | Normal/Insert | Available while spell checking is on: opens a completion menu with suggestions for the word under or before the cursor |

Notes:

- `<Leader><Space>` moves one character to the right and triggers
  insert-mode completion with `<C-X><C-S>` (see `:h ins-completion-menu`).
- If the buffer is `readonly`, pressing `<F2>` always turns spell checking
  off and re-enables `cursorline`, regardless of the previous state.

## Documentation

After installing with a plugin manager, the full documentation is available
inside Vim:

```vim
:Helptags
:help spelling
```