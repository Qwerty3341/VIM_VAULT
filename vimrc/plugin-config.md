```vim
" Coc.nvim

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

nnoremap <C-l> :call coc#float#close_all()<CR>
inoremap <C-l> <Esc>:call coc#float#close_all()<CR>a

inoremap <silent><expr> <CR> coc#pum#visible() ? coc#pum#confirm()
    \: "\<C-g>u\<CR>\<c-r>=coc#on_enter()\<CR>"

function! CheckBackspace() abort
  let col = col('.') - 1
  return !col || getline('.')[col - 1]  =~# '\s'
endfunction

" NerdTree
nnoremap <leader>nt :NERDTreeFocus<CR>
let g:NERDTreeShowHidden = 1
let g:NERDTreeQuitOnOpen = 1
let g:NERDTreeWinSize = 30

" AirLine
let g:airline#extensions#tabline#enabled = 1
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
  autocmd FileType floaterm tnoremap <buffer> <Esc><Esc> <C-\><C-n>0
augroup END

highlight link Floaterm NormalFloat
highlight link FloatermBorder FloatBorder

let g:floaterm_position = 'center'
let g:floaterm_height = 0.9
let g:floaterm_width = 0.9

autocmd QuitPre * silent! FloatermKill!

" vim surround
vnoremap " <Esc>`>a"<Esc>`<i"<Esc>
vnoremap ' <Esc>`>a'<Esc>`<i'<Esc>
vnoremap ( <Esc>`>a)<Esc>`<i(<Esc>
vnoremap [ <Esc>`>a]<Esc>`<i[<Esc>
vnoremap { <Esc>`>a}<Esc>`<i{<Esc>
vnoremap ` <Esc>`>a`<Esc>`<i`<Esc>

" fzf.vim
nnoremap <silent> <leader>f :Files<CR>

" vim-commentary
nnoremap <C-_> :Commentary<CR> 
xnoremap <C-_> :Commentary<CR> 
inoremap <C-_> <Esc>:Commentary<CR>a

" vim visual multi 
let g:VM_maps = {}
let g:VM_maps['I Return'] = ''
let g:VM_maps['I BS'] = ''

let g:VM_show_warnings = 0
let g:VM_default_mappings = 0

" Gruvbox
let g:gruvbox_contrast_dark = "hard"
let g:gruvbox_italic = 1
let g:gruvbox_italicize_comments = 1

let g:terminal_ansi_colors = [
      \ '#282828',  "#cc241d", "#98971a", "#d79921",
      \ '#7c6f64',  "#b16286", "#689d6a", "#a89984",
      \ '#928374',  "#fb4934", "#b8bb26", "#fabd2f",
      \ '#83a598',  "#d3869b", "#8ec07c", "#ebdbb2"
      \ ]

```