# Commands
## Basic file commands
    :help [keyword]         # search for help
    :e [file]               # open file	
    :w                      # save file
    :w [filename]           # save file with given name
    :wq                     # save file and quit vim
    :q!                     # quit without saving


## Basic setting commands
    :set number             # toggle on number of lines
    :set nonumber           # toggle off number of lines
    :set relativenumber     # toggle on relative number of lines
    :set norelativenumber   # toggle off relative number of lines

## Movement 
    k/j/h/l  # move char            at a time (up/down/left/right)
    w/b/e/ge # move word            at a time (start of next/previous word, end of a next/previous word)
    ( / )    # move sentence        at a time (start of previous/next sentence
    { / }    # move paragraph/block at a time (start of previous/next paragraph or block)
    t[char]  # move to                        (right before next given char in line
    f[char]  # move to                        (next given char in line
    F[char]  # move to                        (previous given char in line
    0/$      # move to                        (beginning/end of a line
    ^        # move to                        (beginning word in the line 
    H/L/M    # move to                        (top/bottom/middle of screen
    gg/G     # move to                        (satrt/end of the file

## Editing
### Insert
    i/a         # insert to the left/right of cursor
    A           # insert to the end of this line
    o/O         # add a new line below/above, and enter insert mode
    c[action]   # clear text with action, and enter insert mode
    s/S         # clear current character/line, and enter insert mode

### Change or replace
    r[char]     # replace character below cursor
    R           # enter replace mode instead of insert mode
    ~           # change the case of a character
    >>/<<       # indent or deindent line

### Select, delete, copy, paste
    v/V         # highlight a character/line (move cursor to select text after "v")
    ^v          # select block
    yy/dd       # copies/delete a line
    yw/dw       # copies/delete a word
    p/p         # paste copied text below/above
    y$/D        # copies/delete from cursor to end of the line
    d0          # delete from cursor to beginning of line
    dgg/dG      # delete from cursor to beginning/end of file
    d           # delete hightlighted text
    x           # delete single character

### Other
    u                       # undo last operation
    ^r                      # redo last undo
    .                       # repeat last action
    [n][action/movement]    # do n times eg. 4j 
    q[key]/q                # (in command mode) start/stop recording macro
    ^s/^q                   # freeze/unfreeze Vim

### Userful macros
    @b      # bracket -> next line -> indent

# Settings
## Line numbering
    :set number             # toggle on number of lines
    :set nonumber           # toggle off number of lines
    :set relativenumber     # toggle on relative number of lines
    :set norelativenumber   # toggle off relative number of lines

## Status line
    :set laststatus=2       # 0: never shown, 1: shown only with multiple windows, 2; always
    :set statusline+=
    :set statusline+=\%F    # full path to file
    :set statusline+=\%f    # path to file
    :set statusline+=%=     # switch to the right side

    :set statusline+=\ %y   # filetype
    :set statusline+=\ %{&fileencoding?&fileenconding:&encoding}
    :set statusline+=\ [%{&fileformat}]
    :set statusline+=\ %p%%     # %p%%: current percentage
    :set statusline+=\ %l:%c    # %l: current line, %c: current column
    :set statusline+=\ %L       # %L: total line
    :set statusline+=\


## Tab
    :set tabstop=4          # number of spaces for a tab (default = 8)
    :set shiftwidth=4       # number of spaces for indent (>>, <<)
    :set expandtab          # use spaces to insert tabs
    

## Example setting for .vimrc:

comment with one double quote (") at the beginning of specific line

```
set number

set laststatus=2
set statusline+=
set statusline+=\%F
set statusline+=%=

set statusline+=\ %y
set statusline+=\ %{&fileencoding?&fileenconding:&encoding}
set statusline+=\ [%{&fileformat}]
set statusline+=\ %p%%
set statusline+=\ %l:%c
set statusline+=\

set tabstop=4
set shiftwidth=4
set expandtab
```

# Plugins
## [Vundle (Vim package manager)](https://github.com/VundleVim/Vundle.vim)
  - *Install*:
      `$ git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim`

  - *Add the following lines at the top of .vimrc*:
      ```
      set nocompatible              " be iMproved, required
      filetype off                  " required
      set rtp+=~/.vim/bundle/Vundle.vim
      call vundle#begin()
      Plugin 'VundleVim/Vundle.vim'
      Plugin 'tpope/vim-fugitive'
      Plugin 'tpope/vim-surround'
      Plugin 'scrooloose/nerdtree'
      Plugin 'scrooloose/syntastic'
      Plugin 'airblade/vim-gitgutter'
      Plugin 'altercation/vim-colors-solarized'
      " Plugin 'valloric/youcompleteme'
      Plugin 'nathanaelkane/vim-indent-guides'
      Plugin 'leafgarland/typescript-vim'
      call vundle#end()            " required
      filetype plugin indent on    " required
      ```
  
  - *open vim editor*:
    `$ vim`
    run :PluginInstall in vim editor

  - *Uninstall*:
    remove plugin from config file .vimrc
    quit and restart Vim
    run :PluginClean 

# References and resources:
1. [Best Vim Tips](https://vim.fandom.com/wiki/Best_Vim_Tips)
2. [Vim Doc - Statusline](http://vimdoc.sourceforge.net/htmldoc/options.html#'statusline')
3. [Vim Doc - Tabstop](http://vimdoc.sourceforge.net/htmldoc/options.html#'tabstop')
4. [Learn Vimscript](https://learnvimscriptthehardway.stevelosh.com/chapters/17.html) 
5. [Learn Vimscript the hard way](https://learnvimscriptthehardway.stevelosh.com/)
