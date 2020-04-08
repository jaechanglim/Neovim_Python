# Neovim_Python
neovim setting for python environment

1. Install
* wget https://github.com/neovim/neovim/releases/download/v0.4.3/nvim.appimage
* chmod u+x nvim.appimage
* ln -s nvim.appimage nvim
* curl -fLo ~/.local/share/nvim/site/autoload/plug.vim --create-dirs https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
* pip install pynvim
* pip install jedi
* download afterglow from https://github.com/danilo-augusto/vim-afterglow/blob/master/colors/afterglow.vim to ~/.config/nvim/colors/afterglow.vim
* You can get details of install from https://jdhao.github.io/2018/12/24/centos_nvim_install_use_guide_en/

2. ~/.config/nvim/init.vim
```
call plug#begin('~/.local/share/nvim/plugged')

Plug 'davidhalter/jedi-vim'
Plug 'Shougo/deoplete.nvim', { 'do': ':UpdateRemotePlugins' }
Plug 'zchee/deoplete-jedi'
Plug 'numirias/semshi', {'do': ':UpdateRemotePlugins'}
Plug 'jiangmiao/auto-pairs'
Plug 'sbdchd/neoformat'
Plug 'neomake/neomake'
Plug 'morhetz/gruvbox'
" Indent lines
"Plug 'Yggdroot/indentLine'
" status
Plug 'vim-airline/vim-airline'
call plug#end()

set completeopt-=preview
"let g:SuperTabDefaultCompletionType = "context"
let g:deoplete#enable_at_startup = 1
let g:SuperTabContextDefaultCompletionType = "<c-x><c-o>"
let g:SuperTabDefaultCompletionType = '<C-@>'
let g:neomake_python_enabled_makers = ['pylint']

"call neomake#configure#automake('nrwi', 500)

set smartindent
set tabstop=4
set shiftwidth=4
set expandtab
set colorcolumn=80
colorscheme afterglow
" Uncomment the following to have Vim jump to the last position when
" reopening a file
if has("autocmd")
  au BufReadPost * if line("'\"") > 1 && line("'\"") <= line("$") | exe "normal! g'\"" | endif
endif
" Remove unwanted spaces in line end
autocmd FileType vim autocmd BufWritePre <buffer> %s/\s\+$//e


```
3. ~/.bashrc
```
alias vi='TERM=screen-256color ~/work/programs/nvim -u ~/.config/nvim/init.vim'
```
