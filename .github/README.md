> [!WARNING]
> Since the original version of this plugin offer to modify the asciiart in the configuration, this fork is useless. Please do not use this plugin.

<h1 align="center">🛸 42 Header</h1>

This plugin is a fork of the [diogo-ss](https://github.com/Diogo-ss/42-header.nvim) 42header plugin for 42lyon

## ✨ Features

- Command: `Stdheader`
- Auto update on save (optional)
- Supports `commentstring`
- Supports Git

## 🚀 Showcase

![header](https://raw.githubusercontent.com/kporceil/42lyon-header.nvim/refs/heads/pictures/Screenshot.png)

## 🎈 Setup

<details>
  <summary>📦 Packer.nvim</summary>

```lua
use {
  "kporceil/42lyon-header.nvim",
  cmd = { "Stdheader" },
  config = function()
    require "42header"setup {
      default_map = true, -- Default mapping <F1> in normal mode.
      auto_update = true, -- Update header when saving.
      user = "username", -- Your user.
      mail = "your@email.com", -- Your mail.
    -- add other options.
    }
  end,
}
```

</details>

<details>
  <summary>💤 Lazy.nvim</summary>

```lua
{
  "kporceil/42lyon-header.nvim",
  cmd = { "Stdheader" },
  keys = { "<F1>" },
  opts = {
    default_map = true, -- Default mapping <F1> in normal mode.
    auto_update = true, -- Update header when saving.
    user = "username", -- Your user.
    mail = "your@email.com", -- Your mail.
    -- add other options.
  },
  config = function(_, opts)
    require("42header").setup(opts)
  end,
}
```

</details>

## ⚙ Options

```lua
{
  ---Max header size (not recommended change).
  --length = 80,
  ---Header margin (not recommended change).
  --margin = 5,
  ---Activate default mapping (e.g. F1).
  default_map = true,
  ---Enable auto-update of headers.
  auto_update = true,
  ---Default user.name.
  user = "username",
  ---Default user.email.
  mail = "your@mail.com",
  ---ASCII art.
  --asciiart = { "---", "---", ... },
  ---Git config.
  git = {
    ---Enable Git support.
    enabled = false,
    ---PATH to the Git binary.
    bin = "git",
    ---Use global user.name, otherwise use local user.name.
    user_global = true,
    ---Use global user.email, otherwise use local user.email.
    email_global = true,
  },
}
```

## 🌐 User and Mail

`user` and `mail` can be defined using global variables.

```lua
vim.g.user = "username"
vim.g.mail = "your@mail.com"
```

> **_NOTE:_** The order of priority: `global variables` > `git config (if support enabled)` > `user config`.


## Acknowledgments

Thank to [diogo-ss](https://github.com/Diogo-ss/42-header.nvim)
