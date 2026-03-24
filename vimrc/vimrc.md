```vim
set nocompatible
set number
set relativenumber
set mouse=a
set showcmd
set ruler 
set laststatus=2
set nowrap
set cursorline
set autoread

set wildmenu
set wildmode=longest:full,full

set termguicolors
set noshowmode

set clipboard=unnamedplus
set encoding=UTF-8
syntax on
set showmatch

filetype plugin indent on
set smartindent
set cindent
set expandtab
set completeopt=menu,menuone,noselect
set tabstop=4
set shiftwidth=4
set softtabstop=0
set autoindent

set incsearch
set hlsearch
set ignorecase
set smartcase

set lazyredraw
set updatetime=300

"Configuracion del cursor en los modos
let &t_EI = "\e[2 q"   " Normal → bloque
let &t_SI = "\e[6 q"   " Insert → barra vertical
let &t_SR = "\e[4 q"   " Replace → subrayado

let mapleader=" "

"""""""""""""""""""""""
" Plugins
"""""""""""""""""""""""
so ~/.vim/plugins.vim

"""""""""""""""""""""""
" Plugin config
"""""""""""""""""""""""
so ~/.vim/plugin-config.vim

"""""""""""""""""""""""
" Maps
"""""""""""""""""""""""
so ~/.vim/maps.vim

"""""""""""""""""""""""
" Theme
"""""""""""""""""""""""
set background=dark
colorscheme retrobox

highlight Normal cterm=None
highlight CursorLine ctermbg=236
highlight! link CocInlayHint Comment

```
