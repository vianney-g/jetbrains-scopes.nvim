# jetbrains-scopes.nvim
Author: Vianney Gremmel

## Goal

**Make the Jetbrains scopes available in telescope.nvim**

 You (or some of your colleagues) are using Jetbrains Scopes (e.g: in PyCharm) and you want to
 use them from vim. This plugin allows you to search in the scopes defined
 in your project.

 The scopes must be defined in the .idea/scopes/*.xml files (they may have been
 generated by the IDE).

## Warning

This is a very naive implemention (no xml parsing, naive globs interpretation, etc.).

## Installation

Install the plugin with your favorite plugin manager.

Exemple, with Lazy

```lua
use {
    "vianney-g/jetbrains-scopes.nvim",
    requires = {
        "nvim-lua/plenary.nvim",
        "nvim-telescope/telescope.nvim",
    }
}
```

And then, in your `init.lua`:

```lua
require("jetbrains-scopes")
```

## Usage

 1. Load a scope in neovim.

 ```
 :JBSPickScope
 ```

 2. Fuzzy find inside the scope

 ```
 :JBSSearch
 ```

You can attach these commands to a keymap, for example:

```lua
vim.keymap.set('n', '<leader>jp', ':JBSPick<CR>', { noremap = true, silent = true })
vim.keymap.set('n', '<leader>js', ':JBSSearch<CR>', { noremap = true, silent = true })
```
