# NVCode Colorscheme

![React pic](./assets/react.png)

This colorscheme attempts mirror VSCodes dark+ theme

This Colorscheme requires treesitter and Neovim > 0.5 to look good

## Installing

With `Vim-plug`

```
Plug 'christianchiarulli/nvcode.vim'
Plug 'nvim-treesitter/nvim-treesitter'
```

## Configuring

Just pop this in your `init.vim`

```
lua << EOF
require'nvim-treesitter.configs'.setup {
  ensure_installed = "all", -- one of "all", "maintained" (parsers with maintainers), or a list of languages
  highlight = {
    enable = true,              -- false will disable the whole extension
    disable = { "c", "rust" },  -- list of language that will be disabled
  },
}
EOF
```

And put this in your `init.vim`

```
hi Comment cterm=italic
let g:nvcode_hide_endofbuffer=1
let g:nvcode_terminal_italics=1
let g:nvcode_termcolors=256

syntax on
colorscheme nvcode


" checks if your terminal has 24-bit color support
if (has("termguicolors"))
    set termguicolors
    hi LineNr ctermbg=NONE guibg=NONE
endif
```

(Btw I would appreciate it if someone hard forked this and maintained it so I didn't have to)
