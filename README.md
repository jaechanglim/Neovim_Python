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
Plug 'heavenshell/vim-pydocstring', { 'do': 'make install', 'for': 'python' }

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
let g:pydocstring_formatter = 'google'
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
