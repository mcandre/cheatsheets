# Vi/Vim Cheatsheet

Andrew Pennebaker

https://github.com/mcandre/cheatsheets/blob/master/vim.md

# About

Vim is a highly customizable command line and graphical text editor.

# Documentation

[Emergency vi](http://ergoemacs.org/emacs/emergency_vi.html)

[Vim Tips Wiki](http://vim.wikia.com/wiki/Vim_Tips_Wiki)

[vi and Vim Editors Pocket Reference](http://shop.oreilly.com/product/0636920010913.do)

[Vim Genius](http://vimgenius.com/)

[VIM Adventures](http://vim-adventures.com/)

[The Vi Lovers Home Page](http://thomer.com/vi/vi.html)

# Install

```
$ apt-get install vim

$ brew install macvim --override-system-vim && brew linkapps

C:\> chocolatey install vim
```

By default, Ubuntu uses the `vim.tiny`, which lacks support for arrow key navigation. Use `apt-get install vim` to upgrade to full `vim` with arrow key support.

# Configure

```
~/.vimrc

~/_vimrc
```

[Reference Dotfile](https://github.com/mcandre/dotfiles/blob/master/.vimrc)

# Repositories

[Vundle](https://github.com/gmarik/vundle)

# Basic Commands

## Modes

### Normal

By default, Vim begins in Normal mode, for entering commands. To issue a command, type `Colon`, then the command, then `Enter`. This is represented in Vim documentation with the notation `:command`.

### Insert

From Normal mode, press `i` to switch to Insert mode. Then begin typing text.

To return to Normal mode, press `ESC`.

### Visual

From Normal mode, press `v` to switch to Visual mode. This also allows highlighting text by moving the cursor.

To return to Normal mode, press `ESC`.

## Open or Refresh File/Directory

```
$ vim <file/dir>

$ vim
:e <file/dir>
```

## View File

```
$ view <file/dir>
```

### Windows

```
C:\> vim <file/dir>

gitbash$ vim <file/dir>
```

## Save

```
:w
```

## Save As...

```
:w <filename>

:o
```

## Save all buffers

```
:wall
```

## Quit

```
:q
```

## Force Quit

```
:q!
```

## Undo

```
u
```

## Redo

```
Control+r
```

## Cancel Vim Command

```
ESC
```

## Next Search Result

```
n
```

## Find

```
/<term>
```

`n` next match.

## Replace Global

```
:%s/<term>/<replacement>/g
```

## Search in Directory

```
:grep <term> *.?<file extensions>
```

## Clipboard

Vim will integrate with the OS clipboard, provided that +clipboard is enabled at compile time, and:

```
set clipboard=unnamed
```

is configured in vimrc.

## Cut Line

```
dd
```

## Cut to End of Line

```
D
```

## Cut selected text

1. Use Visual mode (`v`) and arrow keys to select text.
2. `d` - Cut, `y` - Copy

## Copy Lines

```
yy[n]
```

## Paste Lines

```
p
```

# Navigation

## Move Cursor

Arrow keys may also be used, but they require a full `vim` package, provided by default in some Unix installations but not all.

## Left (Visual)

```
h
```

## Down (Visual)

```
j
```

## Up (Visual)

```
k
```

## Right (Visual)

```
l
```

## Start of Line

```
I
```

## End of Line

```
A
```

## Start of Line (Visual)

```
0
```

## End of Line (Visual)

```
$
```

## Page Up

```
Control+b
```

## Page Down

```
Control+f
```

## Go to Line

```
:<n>

<n>G
```

## Go to Start of File

```
:1
```

Or

```
gg
```

## Go to End of File

```
G
```

Or

```
G$
```

## Insert Line Below

```
o
```

## Insert Line Above

```
O
```

## Insert Unicode Literal

```
Control+v u <n>
```

## Delete

```
x
```

# Help

```
:h '<term>
```

# Windows

## Split Windows

```
Control+w, s
```

## Switch Window Directionally

```
Control+W+(direction)
```

## Switch to Next Window

```
Control+w, Control+w
```

## Close Window

```
:hide
```

## Nerd Commenter

1. Select text with Visual mode (`v`).
2. Press `<Leader>c<space>` (`\c `).

## Open Shell

```
:sh
```

## Close Shell

```
Control+d
```

# Repositories

* Vim Scripts http://www.vim.org/scripts/index.php

[Vundle](https://github.com/gmarik/Vundle.vim) is a package manager than can help organize plugins from many different repositories.

# Alternatives

* [vi](http://thomer.com/vi/vi.html) is a precursor to Vim, often installed by default on Unix systems like busybox.
* [Nano](https://github.com/mcandre/cheatsheets/blob/master/nano.md) has a much easier learning curve than Vim.
* [Emacs](https://github.com/mcandre/cheatsheets/blob/master/emacs.md) is comparable to Vim in power, and operates as if in insert mode all of the time.
