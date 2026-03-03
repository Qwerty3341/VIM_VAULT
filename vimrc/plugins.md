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
    Plug 'sheerun/vim-polyglot'


	" Themes
	Plug 'ayu-theme/ayu-vim' 
	Plug 'bluz71/vim-moonfly-colors', { 'as': 'moonfly' }
	Plug 'morhetz/gruvbox'
	Plug 'dracula/vim', { 'as': 'dracula' }


call plug#end()
```