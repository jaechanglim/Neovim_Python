# Neovim_Python
neovim setting for python environment

1. https://jdhao.github.io/2018/12/24/centos_nvim_install_use_guide_en/
2. ~/.config/nvim/init.vim
```
call plug#begin('~/.local/share/nvim/plugged')

Plug 'davidhalter/jedi-vim'
Plug 'Shougo/deoplete.nvim', { 'do': ':UpdateRemotePlugins' }
Plug 'zchee/deoplete-jedi'

call plug#end()

set completeopt-=preview
"let g:SuperTabDefaultCompletionType = "context"
let g:deoplete#enable_at_startup = 1
let g:SuperTabContextDefaultCompletionType = "<c-x><c-o>"
let g:SuperTabDefaultCompletionType = '<C-@>'

set smartindent
set tabstop=4
set shiftwidth=4
set expandtab

```
3. ~/.bashrc
```
alias vi='TERM=screen-256color ~/work/programs/nvim -u ~/.config/nvim/init.vim'
```
