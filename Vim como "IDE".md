# .vimrc
```vim
" Configuracion con vimscript
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


"Temas
set background=dark
" let g:everforest_background = 'hard'   " soft | medium | hard
" let g:everforest_enable_italic = 1
" let g:everforest_better_performance = 1
colorscheme gruvbox
let g:gruvbox_contrast_dark = "hard"
highlight Normal ctermbg=None

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
	Plug 'vim-airline/vim-airline'
	Plug 'vim-airline/vim-airline-themes'
	Plug 'ryanoasis/vim-devicons'

	Plug 'junegunn/fzf', { 'do': { -> fzf#install() } }
	Plug 'junegunn/fzf.vim'

	Plug 'easymotion/vim-easymotion'
	Plug 'mhinz/vim-signify'
	Plug 'tpope/vim-commentary'

	" Temas
	Plug 'sainnhe/everforest'
	Plug 'morhetz/gruvbox'

call plug#end()
```

# ~/.vim/plugin-config.vim
```vim
" Coc.nvim
set nobackup
set nowritebackup

inoremap <silent><expr> <TAB>
      \ coc#pum#visible() ? coc#pum#next(1) :
      \ CheckBackspace() ? "\<Tab>" :
      \ coc#refresh()
inoremap <silent><S-TAB> coc#pum#visible() ? coc#pum#prev(1) : "\<C-h>"

" Make <CR> to accept selected completion item or notify coc.nvim to format
" <C-g>u breaks current undo, please make your own choice
inoremap <silent><expr> <CR> coc#pum#visible() ? coc#pum#confirm()
                              \: "\<C-g>u\<CR>\<c-r>=coc#on_enter()\<CR>"

function! CheckBackspace() abort
  let col = col('.') - 1
  return !col || getline('.')[col - 1]  =~# '\s'
endfunction


augroup CocColors
  autocmd!
  autocmd ColorScheme * call s:coc_colors()
augroup END

function! s:coc_colors() abort
  " Popup menu
  highlight Pmenu guibg=#2d2a2e guifg=#e3e1e4
  highlight PmenuSel guibg=#403d40 guifg=#ffffff gui=bold
  highlight PmenuSbar guibg=#2d2a2e
  highlight PmenuThumb guibg=#5b595c

  " CoC specific
  highlight CocMenuSel guibg=#403d40 guifg=#ffffff gui=bold
  highlight CocSearch guifg=#e3e1e4 gui=underline
  highlight CocPumDetail guifg=#7f8490
  highlight CocPumShortcut guifg=#fc9867
endfunction

" Coc explorer (extension de coc.nvim)
nnoremap <Leader>e :CocCommand explorer<CR>

" NERDTree
nnoremap <Leader>nt :NERDTreeToggle<CR>
let g:NERDTreeQuitOnOpen = 1

" AirLine
let g:airline#extensions#tabline#enabled = 1
let g:airline#extensions#tabline#left_sep = ' '
let g:airline#extensions#tabline#left_alt_sep = '|'
let g:airline#extensions#tabline#buffer_idx_mode = 1

nmap <leader>1 <Plug>AirlineSelectTab1
nmap <leader>2 <Plug>AirlineSelectTab2
nmap <leader>3 <Plug>AirlineSelectTab3
nmap <leader>4 <Plug>AirlineSelectTab4
nmap <leader>5 <Plug>AirlineSelectTab5
nmap <leader>6 <Plug>AirlineSelectTab6
nmap <leader>7 <Plug>AirlineSelectTab7
nmap <leader>8 <Plug>AirlineSelectTab8
nmap <leader>9 <Plug>AirlineSelectTab9

nnoremap <Leader>] :bnext<CR>
nnoremap <Leader>[ :bprevious<CR>
nnoremap <Leader>q :bprevious \| bdelete #<CR>

" Easymotion
nmap s <Plug>(easymotion-s2)
nmap t <Plug>(easymotion-t2)

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

nnoremap <Leader>l :vertical resize +10<CR>
nnoremap <Leader>h :vertical resize -10<CR>
nnoremap <Leader>k :resize +5<CR>
nnoremap <Leader>j :resize -5<CR>
```