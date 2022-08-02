# nav.nvim
A Neovim implementation of [nav](https://github.com/kaybinwang/nav) in Lua.

## Requirements
- Neovim 0.7+ since we depend on the `nvim_create_user_command` API.

## Installation
Install using your favorite package manager.

### Packer Example
```lua
require("packer").startup(function(use)
   -- other plugins ...

   use "kaybinwang/nav.nvim"
)
```

## Usage
You can use the `Nav` command to create shortcuts to directories that you visit often.
```vim
:Nav add pp ~/personal/projects  " create a new shortcut
:Nav to pp                       " navigate to the shortcut
```

You can also manage your shortcuts using `:Nav update` and `:Nav remove`.
```vim
:Nav update pp ~/new/personal/projects  " update the shortcut
:Nav remove pp                          " delete the shortcut
```

Finally, you can see what shortcuts you have defined by using nav list.
```vim
:Nav list
```

Please refer to `:help nav` for more documentation on the commands.

## Configuration
By default, `:Nav` stores your shortcuts in `~/.config/nav`. However, you can set your own custom directory by setting the `NAV_PATH` environment variable. For example,

```bash
export NAV_PATH=/path/to/shortcuts
source /path/to/nav.sh
```

TODO add configuration that can modify
- subcommand names
- nav_path
