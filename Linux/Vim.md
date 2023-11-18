
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

### Shortcuts

```c
<C-w-w> Change buffer
<⬆️-v> select whole line
<⬆️-a> insert at end of line
<v-i-w> select word
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