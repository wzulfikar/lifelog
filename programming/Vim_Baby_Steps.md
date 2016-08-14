# Vim Baby Steps
- start with `:` and then command. eg:
  - to edit, type in `:e` and then filename
- store configuration in your `~/.vimrc` file

## Commong Plugins
**vim-vinegar** 
- `-` enter vim-vinegar (display current directory)
- `⬆ + d` : delete file/directory
- `d` : create directory
- `⬆ + 5` : create directory

**ctrlp**
- `ctrl + p` and start fuzzy-search of file/dir

**nerdtree**
- `ctrl + h` go to sidebar
- `ctrl + k` go to file
- `:NERDTree` display sidebar
- `:CtrlPBufTag` display tags


- `gg` back to top
- `:(line number` go to line number
- `/(keyword)` go to first match, press `n` to go to next match
- `bd` close editor


```
"~/.vimrc

set nocompatible " we want the latest Vim settings/options

so ~/.vim/plugins.vim

syntax enable

set linespace=15set backspace=indent,eol,start " make backspace behave like every other editorlet mapleader = ',' " the default is \, but a comma is much betterset number " activate line numbercolorscheme peachpuff

"-------------- Mappings --------------"

"make NERDTREE easier to toggle.
"nmap <D-1> :NERDTreeToggle<cr>

nmap <c-R> :CtrlPBufTag<cr>
```

```
"~/.vim/plugins.vim

filetype off " required

" set the runtime path to include Vundle and initialize
set rtp+=~/.vim/bundle/Vundle.vim
call vundle#begin()

" let Vundle manage Vundle, required
Plugin 'VundleVim/Vundle.vim'
Plugin 'tpope/vim-vinegar'
Plugin 'scrooloose/nerdtree'
Plugin 'ctrlpvim/ctrlp.vim'
Plugin 'vim-airline/vim-airline'
Plugin 'vim-airline/vim-airline-themes'
Plugin 'airblade/vim-gitgutter'Plugin 'tpope/vim-fugitive'

" All of your Plugins must be added before the following line
call vundle#end() " required
filetype plugin indent on " required

```