```vim
" write y quit
nmap <Leader>w :w<CR>
nmap <Leader>q :q<CR>

" Tabs 
inoremap <S-Tab> <C-d>
nnoremap <S-Tab> <<
nnoremap <Tab> >>
vnoremap <Tab> >gv
vnoremap <S-Tab> <gv

" Surround
xnoremap s" c"<C-r>""<Esc>
xnoremap s' c'<C-r>"'<Esc>
xnoremap s( c(<C-r>")<Esc>
xnoremap s[ c[<C-r>"]<Esc>
xnoremap s{ c{<C-r>"}<Esc>
xnoremap s` c`<C-r>"`<Esc>

" Ajustar tamanio de paneles
nnoremap <C-S-Right> :vertical resize +10<CR>
nnoremap <C-S-Left>  :vertical resize -10<CR>
nnoremap <C-S-Up>    :resize +5<CR>
nnoremap <C-S-Down>  :resize -5<CR>

" --- netrw estilo nerdtree ---
nmap <Leader>e :Lexplore<CR>

let g:netrw_banner = 0
let g:netrw_liststyle = 3
let g:netrw_special_syntax = 1
let g:netrw_browse_split = 4
let g:netrw_altv = 1
let g:netrw_winsize = 25
let g:netrw_hide = 1
let g:netrw_keepdir = 0

" Backspace mejorado
vnoremap <BS> "_d
nnoremap <BS> "_x

" Enter mejorado
nnoremap <CR> o<Esc>

" Change mejorado 
nnoremap c "_c
xnoremap c "_c

```