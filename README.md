# inc-rename.nvim

A tiny Neovim plugin that provides a command for LSP renaming with immediate visual
feedback thanks to Neovim's command preview feature. Requires Neovim nightly (0.8).

<div align="center">
<video src="https://user-images.githubusercontent.com/40792180/171936247-9a4af4f8-fcc6-4c0c-a230-5d65339cd29c.mp4" width="85%">
</div>

## Installation
Install using your favorite package manager and call the `setup` function.
Here is an example using `packer.nvim`:
```lua
use {
  "smjonas/inc-rename.nvim",
  config = function()
    require("inc_rename").setup()
  end,
}
```

## Usage
Simply type `:IncRename <new_name>` while your cursor is on an LSP identifier.
You could also create a keymap that types out the command name for you so you only have to
type the new name:
```lua
vim.keymap.set("n", "<leader>r", ":IncRename ")
```

## Customization
You can override the default configuration by passing a Lua table to the `setup` function.
The default options are:
```lua
require("inc_rename.nvim").setup {
  cmd_name = "IncRename", -- the name of the command
  hl_group = "Substitute", -- the highlight group used for highlighting the new identifier's name
}
```