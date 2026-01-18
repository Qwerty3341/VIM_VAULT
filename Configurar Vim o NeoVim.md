- Para el caso de nvim
	1. Entrar en `.config/nvim`
	2. Se edita `init.vim`
- Para vim 
	1. Se entra en el `.vimrc`
# En neovim se usa
Para poner el mismo archivo de configuración de vim para no tener dos archivos de configuración 
```bash
set runtimepath^=~/.vim runtimepath+=~/.vim/after
let &packpath=&runtimepath
source ~/.vimrc
```
# Configuración básica
```
set number
set relativenumber     
set numberwidth=1
set mouse=a
set showcmd
set ruler 
set laststatus=2
set nowrap
set cursorline
set wildmenu
set wildmode=longest:full,full
set termguicolors
set noshowmode
set clipboard=unnamedplus
set encoding=utf-8
syntax enable
set showmatch
filetype plugin indent on
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
```