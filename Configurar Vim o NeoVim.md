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
" ---- Interfaz ----
set number              " Muestra números de línea absolutos
set relativenumber      " Muestra números de línea relativos al cursor
set numberwidth=1       " Ancho mínimo de la columna de números
set mouse=a             " Habilita el uso del mouse
set showcmd             " Muestra comandos incompletos
set ruler               " Muestra la posición del cursor
set laststatus=2        " Muestra siempre la barra de estado
set nowrap              " Evita que las líneas largas se partan visualmente
set cursorline          " Resalta la línea donde está el cursor
highlight CursorLine cterm=NONE ctermbg=236 guibg=#303030 " Color del fondo de la línea actual en terminal
set background=dark

" ---- Portapapeles ----
set clipboard=unnamedplus " Usa el portapapeles del sistema

" ---- Codificación y sintaxis ----
set encoding=utf-8      " Usa UTF-8 como codificación
syntax enable           " Activa el resaltado de sintaxis
set showmatch           " Resalta pares coincidentes
set smartindent         " Agrega indentación extra en estructuras tipo `{ }`, `if`, `for`, etc.
filetype plugin indent on " Lo mismo que smartindent pero con mayor soporte a lenguajes

" ---- Tabulaciones (TAB reales) ----
set noexpandtab         " Usa tabuladores reales, no espacios
set tabstop=4           " Un TAB se muestra como 4 columnas
set shiftwidth=4        " Indentación con >> y <<
set softtabstop=0       " Evita simulación de espacios
set autoindent          " Copia la indentación de la línea anterior 

" ---- Pluggins ----
call plug#begin()
	Plug 'autor/repoDelPluggin'
call plug#end()
```