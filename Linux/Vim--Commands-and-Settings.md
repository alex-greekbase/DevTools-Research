# Commands
## basic file commands
    :help [keyword]         # search for help

    :e [file]               # open file	

    :w                      # save file

    :w [filename]           # save file with given name

    :wq                     # save file and quit vim

    :q!                     # quit without saving


## basic setting commands
    :set number             # toggle on number of lines

    :set nonumber           # toggle off number of lines

    :set relativenumber     # toggle on relative number of lines

    :set norelativenumber   # toggle off relative number of lines


## movement 
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

## editing
### insert
    i/a         # insert to the left/right of cursor

    A           # insert to the end of this line

    o/O         # add a new line below/above, and enter insert mode

    c[action]   # clear text with action, and enter insert mode

    s/S         # clear current character/line, and enter insert mode

### change or replace
    r[char]     # replace character below cursor

    R           # enter replace mode instead of insert mode

    ~           # change the case of a character


### select, delete, copy, paste
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

### other
    u                       # undo last operation

    ^r                      # redo last undo

    .                       # repeat last action

    [n][action/movement]    # do n times eg. 4j 

    q[key]/q                # (in command mode) start/stop recording macro

# Settings

Setting example:

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

1. vim settings source file
    ~/.vimrc

2. number of lines
    :set number           # toggle on number of lines
    :set nonumber         # toggle off number of lines
    :set relativenumber   # toggle on relative number of lines
    :set norelativenumber # toggle off relative number of lines

3. status line
    :set laststatus=2
    :set statusline+=
    :set statusline=+\%F

# References and resources:
1. [Best Vim Tips](https://vim.fandom.com/wiki/Best_Vim_Tips)


