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
if has("vim") || has("nvim")

" ─── Interfaz ───────────────────────────────────────
set number              " Muestra números de línea absolutos
set relativenumber      " Muestra números de línea relativos al cursor
set numberwidth=1       " Ancho mínimo de la columna de números
set mouse=a             " Habilita el uso del mouse
set showcmd             " Muestra comandos incompletos
set ruler               " Muestra la posición del cursor
set laststatus=2        " Muestra siempre la barra de estado
set noshowmode          " Oculta -- INSERT --

" ─── Portapapeles ───────────────────────────────────
set clipboard=unnamedplus " Usa el portapapeles del sistema

" ─── Codificación y sintaxis ────────────────────────
set encoding=utf-8      " Usa UTF-8 como codificación
syntax enable           " Activa el resaltado de sintaxis
set showmatch           " Resalta pares coincidentes

" ─── Tabulaciones (TAB reales) ──────────────────────
set noexpandtab         " Usa tabuladores reales, no espacios
set tabstop=4           " Un TAB se muestra como 4 columnas
set shiftwidth=4        " Indentación con >> y <<
set softtabstop=0       " Evita simulación de espacios

endif
```