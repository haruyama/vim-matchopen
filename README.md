# MatchOpen

A simple [Vim](http://www.vim.org/) plugin to highlight the last opened, 
but unclosed delimiter. Based on Vim's own `matchparen.vim`.

This version([haruyama/vim-matchopen](https://github.com/haruyama/vim-matchopen)) also highlights the first close delimiter in context.

Original version: [arnar/vim-matchopen](https://github.com/arnar/vim-matchopen)

Example:

    synIDattr(synID(line("."), col("."), 0), "name") 
                   ^  ^                   ^
                   |  if cursor is here   |
                   this is highlighted    this is highlighted

Note: This is a preliminary version for testing. Only works for regular
parenthesis and has no documentation.

Warning: Like `matchparen.vim`, this installs an autocommand run whenever
the cursor is moved. It may be too slow if you have large folds collapsed
in the current window, or very long lines. It can be turned it off with 
`:NoMatchLastOpen`, and on again with `:DoMatchLastOpen`.

## Setting examples

```vim
"Set searchpairpos() timeout(msec). Default value is 3.
"The longer value you set, the larger range will be searched.
"But you will feel that operations are heavier.
"Note: The value must not be negative. 
"      A zero value is like not giving the argument.
let g:matchopen_searchpairpos_timeout = 5
```
