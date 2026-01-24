# .vimrc
```vim
set number
set relativenumber
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
set encoding=UTF-8
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

" set cmdheight=2
set lazyredraw
set updatetime=300

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


"Temas
set background=dark
let g:gruvbox_contrast_dark = "hard"
colorscheme gruvbox
" colorscheme sonokai
" colorscheme embark
" highlight Normal ctermbg=NONE

```

# ~/.vim/plugins.vim

```vim
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
	Plug 'ryanoasis/vim-devicons'

	Plug 'junegunn/fzf', { 'do': { -> fzf#install() } }
	Plug 'junegunn/fzf.vim'

	Plug 'easymotion/vim-easymotion'
	Plug 'mhinz/vim-signify'
	Plug 'tpope/vim-commentary'

	" Temas
    Plug 'morhetz/gruvbox'
	Plug 'sainnhe/sonokai'
	Plug 'embark-theme/vim', { 'as': 'embark', 'branch': 'main' }
call plug#end()

```

# ~/.vim/plugin-config.vim
```vim
" ====================
" Configuración de coc
" ====================
set nobackup
set nowritebackup
set signcolumn=yes

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

inoremap <silent><expr> <c-space> coc#refresh()

" augroup CocColors
"   autocmd!
"   autocmd ColorScheme * call s:coc_colors()
" augroup END

" function! s:coc_colors() abort
"   Popup menu
"   highlight Pmenu guibg=#2d2a2e guifg=#e3e1e4
"   highlight PmenuSel guibg=#403d40 guifg=#ffffff gui=bold
"   highlight PmenuSbar guibg=#2d2a2e
"   highlight PmenuThumb guibg=#5b595c

"   " CoC specific
"   highlight CocMenuSel guibg=#403d40 guifg=#ffffff gui=bold
"   highlight CocSearch guifg=#e3e1e4 gui=underline
"   highlight CocPumDetail guifg=#7f8490
"   highlight CocPumShortcut guifg=#fc9867
" endfunction

" ====================
"Configuración de vim buffet
" ====================
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
let g:buffet_powerline_separators = 1
let g:buffet_show_only_buffers = 1
let g:buffet_show_index = 1
let g:buffet_tab_icon = "\uf00a"
let g:buffet_left_trunc_icon = "\uf0a8"
let g:buffet_right_trunc_icon = "\uf0a9"
autocmd FileType nerdtree setlocal nobuflisted


function! g:BuffetSetCustomColors() abort
  highlight! link BuffetCurrentBuffer StatusLine
  highlight! link BuffetOtherBuffer StatusLineNC
endfunction

augroup BuffetColors
  autocmd!
  autocmd ColorScheme * call g:BuffetSetCustomColors()
augroup END


" ====================
"Configuracion de nerdtree
" ====================
" let g:NERDTreeWinSize = 30

" ====================
"Configuracion de lightline
" ====================
let g:lightline = {
      \ 'colorscheme': 'one',
      \ 'enable': { 'tabline': 0 }
      \ }

```

# Maps
```vim
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

nnoremap <Leader>l :vertical resize +10<CR>
nnoremap <Leader>h :vertical resize -10<CR>
nnoremap <Leader>k :resize +5<CR>
nnoremap <Leader>j :resize -5<CR>

```