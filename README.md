# My AstroNvim Configuration with AI Code Completion

---

**NOTE:** This guide is intended for AstroNvim version 4 and above. Ensure that Neovim is already installed on your system.

## Personal AstroNvim Configuration

The **/lua/community.lua** file contains comprehensive configurations curated by the AstroNvim community for various programming languages:

```lua
---@type LazySpec
return {
  "AstroNvim/astrocommunity",
  { import = "astrocommunity.pack.lua" },
  { import = "astrocommunity.pack.cpp" },
  { import = "astrocommunity.pack.typescript" },
  { import = "astrocommunity.pack.python" },
  { import = "astrocommunity.pack.php" },
  { import = "astrocommunity.pack.markdown" },
  -- Customize with your own plugin imports
}
```

Each language setup includes a debugger, code completion, code formatter, and linter. You can tailor the **lua/community.lua** file to meet your specific development needs.

### AI Code Completion

I utilize [supermaven](https://supermaven.com/), an impressive AI code completion tool.

To disable it, simply remove the following lines from **lua/plugins/user.lua**:

```lua
-- supermaven
{
  "supermaven-inc/supermaven-nvim",
  config = function()
    require("supermaven-nvim").setup {
      -- Your configuration here
      -- See https://github.com/supermaven-inc/supermaven-nvim/blob/main/doc/supermaven-nvim.txt
      keymaps = {
        accept_suggestion = "<C-a>",
        clear_suggestion = "<C-]>",
        accept_word = "<C-j>",
      },
      ignore_filetypes = { txt = true },
    }
  end,
},
```

### Keybindings

I adhere to the default AstroNvim keybindings, with specific adjustments for:

- **supermaven:**

  - <kbd>C-a</kbd> : Accept suggestion
  - <kbd>C-]</kbd> : Clear suggestion
  - <kbd>C-j</kbd> : Accept word

- **zen mode:**
  - <kbd>Space</kbd> + <kbd>z</kbd> + <kbd>z</kbd> : Toggle zen mode
    (Default leader is <kbd>Space</kbd>)

## 🛠️ Installation

#### Backup your current Neovim configuration

- For Linux/MacOS:

```shell
mv ~/.config/nvim ~/.config/nvim.bak
mv ~/.local/share/nvim ~/.local/share/nvim.bak
mv ~/.local/state/nvim ~/.local/state/nvim.bak
mv ~/.cache/nvim ~/.cache/nvim.bak
```

- For Windows:

```shell
Move-Item $env:LOCALAPPDATA\nvim $env:LOCALAPPDATA\nvim.bak
Move-Item $env:LOCALAPPDATA\nvim-data $env:LOCALAPPDATA\nvim-data.bak
```

#### Clone the repository

Ensure to remove the initial **.git** folder:

```shell
rm -rf ~/.config/nvim/.git
```

Then clone the repository to your configuration folder.

- For Linux/MacOS:

```shell
git clone https://github.com/alaminedione/my-nvim-astronvim-config ~/.config/nvim
```

- For Windows:

```shell
git clone --depth 1 https://github.com/alaminedione/my-nvim-astronvim-config $env:LOCALAPPDATA\nvim
```

#### Start Neovim

```shell
nvim
```

#### Credits

- [AstroNvim](https://astronvim.com/)
- [AstroNvim Community](https://github.com/AstroNvim/astrocommunity)
- [supermaven](https://supermaven.com/)
