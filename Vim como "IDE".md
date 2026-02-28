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
	Plug 'tpope/vim-surround'

	Plug 'junegunn/fzf', { 'do': { -> fzf#install() } }
	Plug 'junegunn/fzf.vim'
	Plug 'voldikss/vim-floaterm'

	Plug 'easymotion/vim-easymotion'
	Plug 'mhinz/vim-signify'
	Plug 'tpope/vim-commentary'


	" Themes
	Plug 'ayu-theme/ayu-vim' 
	Plug 'bluz71/vim-moonfly-colors', { 'as': 'moonfly' }
	Plug 'morhetz/gruvbox'


call plug#end()
```

# ~/.vim/plugin-config.vim
```vim
" Coc.nvim
set nobackup
set nowritebackup

nmap <silent><nowait> gd <Plug>(coc-definition)
nmap <silent><nowait> gy <Plug>(coc-type-definition)
nmap <silent><nowait> gi <Plug>(coc-implementation)
nmap <silent><nowait> gr <Plug>(coc-references)

inoremap <silent><expr> <C-Space>
      \ coc#pum#visible()
      \ ? coc#pum#cancel()
      \ : coc#refresh()

inoremap <silent><expr> <C-@>
      \ coc#pum#visible()
      \ ? coc#pum#cancel()
      \ : coc#refresh()

inoremap <silent><expr> <TAB>
      \ coc#pum#visible() ? coc#pum#next(1):
      \ CheckBackspace() ? "\<Tab>" :
      \ coc#refresh()


inoremap <silent><expr> <C-l>
      \ coc#float#has_float()
      \ ? coc#float#close_all()
      \ : CocAction('showSignatureHelp')

" Make <CR> to accept selected completion item or notify coc.nvim to format
" <C-g>u breaks current undo, please make your own choice
inoremap <silent><expr> <CR> coc#pum#visible() ? coc#pum#confirm()
    \: "\<C-g>u\<CR>\<c-r>=coc#on_enter()\<CR>"


function! CheckBackspace() abort
  let col = col('.') - 1
  return !col || getline('.')[col - 1]  =~# '\s'
endfunction

" augroup CocColors
"   autocmd!
"   autocmd ColorScheme * call s:coc_colors()
" augroup END

" function! s:coc_colors() abort
"   " Popup menu
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

" Easymotion
nmap s <Plug>(easymotion-s2)
nmap t <Plug>(easymotion-t2)

" vim-floaterm
nnoremap <C-t> :FloatermToggle<CR>
tnoremap <C-t> <C-\><C-n>:FloatermToggle<CR>

augroup FloatermMappings
  autocmd!
  autocmd FileType floaterm tnoremap <buffer> <Esc><Esc> <C-\><C-n>
augroup END

highlight link Floaterm NormalFloat
highlight link FloatermBorder FloatBorder

" vim surround
vnoremap "  <Esc>`>a"<Esc>`<i"<Esc>
vnoremap '  <Esc>`>a'<Esc>`<i'<Esc>
vnoremap (  <Esc>`>a)<Esc>`<i(<Esc>
vnoremap [  <Esc>`>a]<Esc>`<i[<Esc>
vnoremap {  <Esc>`>a}<Esc>`<i{<Esc>
vnoremap `  <Esc>`>a`<Esc>`<i`<Esc>

" fzf.vim
nnoremap <silent> <leader>f :Files<CR>

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

nnoremap <C-S-Right> :vertical resize +10<CR>
nnoremap <C-S-Left>  :vertical resize -10<CR>
nnoremap <C-S-Up>    :resize +5<CR>
nnoremap <C-S-Down>  :resize -5<CR>

```