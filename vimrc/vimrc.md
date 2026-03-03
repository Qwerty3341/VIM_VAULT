```vim
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

"Configuracion de los modos
let &t_EI = "\e[2 q"   " Normal → bloque
let &t_SI = "\e[6 q"   " Insert → barra vertical
let &t_SR = "\e[4 q"   " Replace → subrayado

let mapleader=" "

"""""""""""""""""""""""
" Plugins
"""""""""""""""""""""""
so ~/.vim/plugins.vim

"""""""""""""""""""""""
" Configuración de plugins
"""""""""""""""""""""""
so ~/.vim/plugin-config.vim

"""""""""""""""""""""""
" Atajos
"""""""""""""""""""""""
so ~/.vim/maps.vim


"""""""""""""""""""""""
" Temas
"""""""""""""""""""""""

let ayucolor="dark"
colorscheme ayu

" set background=dark
" colorscheme gruvbox
" let g:gruvbox_contrast_dark = "hard"
" let g:terminal_ansi_colors = [       
"         \ '#282828',  "#cc241d", "#98971a", "#d79921",
"         \ '#7c6f64',  "#b16286", "#689d6a", "#a89984",
"         \ '#928374',  "#fb4934", "#b8bb26", "#fabd2f",
"         \ '#83a598',  "#d3869b", "#8ec07c", "#ebdbb2"
"         \ ]

" Barra en la seleccion
highlight Normal cterm=None
```
