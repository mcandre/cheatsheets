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
$HOME/.vimrc

%HOME%/_vimrc
```

[Reference Dotfile](https://github.com/mcandre/dotfiles/blob/master/.vimrc)

# Repositories / Plugins

[vim-plug](https://github.com/junegunn/vim-plug)

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

## Reload buffer from file system contents

```
:e!
```

## Quit

```
:q
```

## Force Quit

```
:q!
```

## Quit all windows

```
:qa
```

## Forcibly quit all windows

```
:qa!
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

## Find (until end of buffer)

```
/<term>
```

`n` next match.

## Find and Replace (until end of buffer)

```
:%s/<term>/<replacement>/gc
```

`a` - replaces all occurences.

`y` - replaces current match.

`n` - skips over current match.

## Search in Directory

```
:grep <term> *.?<file extensions>
```

## Hotkey syntax

http://vimhelp.appspot.com/intro.txt.html#key-notation

### Repeat Command

```
:%<command>
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

### Copy all lines

```
:%y Enter
```

## Paste Lines

```
p
```

## Paste Lines (Insert)

```
Control+r, +
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

## Back one Word (non-punctuation characters)

```
b
```

## Forward one Word (non-punctuation characters)

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

## Split Windows into Top vs Bottom

```
Control+w, s
```

## Switch Window into Left vs Right

```
Control+W, v
```

## Switch to Next Window

```
Control+w, Control+w
```

## Close Window

```
:hide
```

## Switch buffer

```
:b <name>
```

## Toggle commenting

1. Select text with Visual mode (`v`).
2. Press `gc`.

Or

1. Navigate to the desired line.
2. Press `gcc`.

## Open Shell

```
:sh
```

## Close Shell

```
Control+d
```

# Fix common problems

Vim doesn't have the most intuitive defaults. Here are some snippets you can insert into your `$HOME/.vimrc` / `$HOME/_vimrc` in order to fix common problems.

## Delete (backspace) broken in insert mode in Mac OS X

`set backspace=2`

Or use MacVim

## Lack of line numbers

`set number`

## Lack of syntax highlighting

`syntax on`

## Code folding too deep

```
set foldmethod=syntax
set foldcolumn=1
set foldlevelstart=20
```

For more helpful snippets, see https://github.com/mcandre/dotfiles/blob/master/.vimrc

# Other repositories

* Vim Scripts http://www.vim.org/scripts/index.php

# Alternatives

* [vi](http://thomer.com/vi/vi.html) is a precursor to Vim, often installed by default on Unix systems like busybox.
* [Nano](https://github.com/mcandre/cheatsheets/blob/master/nano.md) has a much easier learning curve than Vim.
* [Emacs](https://github.com/mcandre/cheatsheets/blob/master/emacs.md) is comparable to Vim in power, and operates as if in insert mode all of the time.
