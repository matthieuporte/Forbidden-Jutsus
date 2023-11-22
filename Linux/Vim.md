
### Plugins

```bash
call vundle#begin()

    Plugin 'VundleVim/Vundle.vim'
    Plugin 'tpope/vim-sensible'
    Plugin 'preservim/nerdtree'
    Plugin 'itchyny/lightline.vim'
    Plugin 'tpope/vim-commentary'

call vundle#end()
```

### Commands

_open a new file in a split panel_

```bash
:sp filename
```

*Substitutions*
```
:%s/old/new/g #change for all file
:#,#s/old/new/g #change between lines
```

*Paste output in file*
```
:r (command/file)
```


*Save file as*
```
:sav(eas) file
```

*Search for pattern in multiple files*
```
:vim[grep] /pattern/ {`{file}`} 
```

*clear vim highlighting*
```
:noh
```

### Shortcuts

```c
<C-w-w> Change buffer
<⬆️-v> select whole line
<⬆️-a> insert at end of line
<⬆️-d> deletes till end of line
<⬆️-k> open man page for word under cursor
<v-i-w> select word
<c-i-w> replace word
<#> find next occ of word
<"+y> copy to main clipboard
<"+p> paste from main clipboard
<z+z> scrolls to the middle of the term
```

### NERDTree

```c
<⬆️-i> toggle hidden files
<?> show help
```

### .vimrc
```shell
:set tw=80
```

### Vim folding commands

```
zf#j creates a fold from the cursor down # lines.
zf/ string creates a fold from the cursor to string .
zj moves the cursor to the next fold.
zk moves the cursor to the previous fold.
za toggle a fold at the cursor.
zo opens a fold at the cursor.
zO opens all folds at the cursor.
zc closes a fold under cursor. 
zm increases the foldlevel by one.
zM closes all open folds.
zr decreases the foldlevel by one.
zR decreases the foldlevel to zero -- all folds will be open.
zd deletes the fold at the cursor.
zE deletes all folds.
[z move to start of open fold.
]z move to end of open fold.
```