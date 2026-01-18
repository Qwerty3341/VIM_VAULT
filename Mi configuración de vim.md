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

let &t_EI = "\e[2 q"   " Normal → bloque
let &t_SI = "\e[6 q"   " Insert → barra vertical
let &t_SR = "\e[4 q"   " Replace → subrayado

let mapleader=" "

"""""""""""""""""""""""
"       Plugins
"""""""""""""""""""""""

call plug#begin()
		
	" IDE
	Plug 'scrooloose/nerdtree'    
	Plug 'neoclide/coc.nvim', {'branch': 'release'}
	Plug 'christoomey/vim-tmux-navigator'
	Plug 'jiangmiao/auto-pairs'
	Plug 'alvan/vim-closetag'
	Plug 'yggdroot/indentline'
	Plug 'itchyny/lightline.vim'
	Plug 'bagrat/vim-buffet'

	Plug 'junegunn/fzf', { 'do': { -> fzf#install() } }
	Plug 'junegunn/fzf.vim'

	Plug 'easymotion/vim-easymotion'
	Plug 'mhinz/vim-signify'
	Plug 'tpope/vim-commentary'
	" Temas
    Plug 'morhetz/gruvbox'
	" Plug 'sainnhe/everforest'

call plug#end()


" Configuración de coc
let g:coc_global_extensions = [
    \ 'coc-json',
    \ 'coc-html',
    \ 'coc-css',
    \ 'coc-tsserver',
    \ 'coc-pyright',
    \ 'coc-java',
    \ ]

function! CheckBackspace() abort
  let col = col('.') - 1
  return !col || getline('.')[col - 1] =~# '\s'
endfunction

inoremap <silent><expr> <TAB>
      \ coc#pum#visible() ? coc#pum#next(1) :
      \ CheckBackspace() ? "\<Tab>" :
      \ coc#refresh()

inoremap <silent><expr> <S-TAB>
      \ coc#pum#visible() ? coc#pum#prev(1) : "\<C-h>"

inoremap <silent><expr> <CR>
      \ coc#pum#visible() ? coc#pum#confirm() : "\<CR>"


"Configuración de vim buffet
nmap <leader>1 <Plug>BuffetSwitch(1)
nmap <leader>2 <Plug>BuffetSwitch(2)
nmap <leader>3 <Plug>BuffetSwitch(3)
nmap <leader>4 <Plug>BuffetSwitch(4)
nmap <leader>5 <Plug>BuffetSwitch(5)
nmap <leader>6 <Plug>BuffetSwitch(6)
nmap <leader>7 <Plug>BuffetSwitch(7)
nmap <leader>8 <Plug>BuffetSwitch(8)
nmap <leader>9 <Plug>BuffetSwitch(9)

let g:buffet_show_tabline = 1
let g:buffet_show_only_buffers = 1
let g:buffet_show_index = 1
autocmd FileType nerdtree setlocal nobuflisted

let g:lightline = {
      \ 'enable': { 'tabline': 0 }
      \ }

function! g:BuffetSetCustomColors()
  hi! BuffetCurrentBuffer cterm=NONE ctermbg=5 ctermfg=8 guibg=#00FF00 guifg=#000000
endfunction

"Configuracion de nerdtree
let g:NERDTreeWinSize = 30

" Atajos
nmap <Leader>w :w<CR>
nmap <Leader>q :q<CR>

inoremap <S-Tab> <C-d>
nnoremap <S-Tab> <<
nnoremap <Tab> >>
vnoremap <Tab> >gv
vnoremap <S-Tab> <gv

nnoremap <Leader>nt :NERDTreeToggle<CR>

nmap s <Plug>(easymotion-s2)
nmap t <Plug>(easymotion-t2)

"Temas
set background=dark
let g:gruvbox_contrast_dark = "hard"
colorscheme gruvbox
highlight Normal ctermbg=NONE
```