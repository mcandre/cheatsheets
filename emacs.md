# Emacs Cheatsheet

Andrew Pennebaker

https://github.com/mcandre/cheatsheets/blob/master/emacs.md

# About

GNU Emacs is a highly customizable command line and graphical text editor.

# Documentation

[EmacsWiki](http://emacswiki.org/)

[GNU Emacs Pocket Reference](http://shop.oreilly.com/product/9781565924963.do)

[GNU Emacs Manual](https://www.gnu.org/software/emacs/manual/html_node/emacs/index.html)

[An Introduction to Programming in Emacs Lisp](https://www.gnu.org/software/emacs/manual/html_node/eintr/index.html)

[GNU Emacs Manuals Online](https://www.gnu.org/software/emacs/manual/index.html)

# Install

```
$ apt-get install emacs

$ brew install --cocoa emacs

C:\> chocolatey install Emacs
```

[emacs-24.2.msi](http://www.yellosoft.us/helpers#emacs)

# Configure

```
~/.emacs
```

[Reference Dotfile](https://github.com/mcandre/dotfiles/blob/master/.emacs)

When troubleshooting Emacs, it is often useful to skip loading `~/.emacs` configuration:

```
$ emacs -Q ...
```

# Hotkey Notation

* `C-` = `Control`
* `M-` = `Alt` ("Meta" key)
* `S-` = `Shift`
* `key-key key-key key-key...` = Hotkeys are pressed in order, not simultaneously.

# Evaluate Elisp Code

```
M-: (<code...>)

M-x <code>
```

# System Commands

```
M-x shell

M-x eshell

M-! <command>
```

## Repeat last command

```
M-p, RET
```

## Ncurses Terminals

For ncurses-style programs that erase the screen, use:

```
M-x term
```

In term-mode, `C-x ...` commands should be typed as `C-c ...`.

# Packages

```
M-: (package-refresh-contents)

M-: (package-install '<package>)
```

# Repositories

[Marmalade](http://marmalade-repo.org/)

[MELPA](http://melpa.milkbox.net/)

# Basic Commands

## Open File/Directory

```
$ emacs <file/dir>

$ emacs
C-x C-f <file/dir>
```

## View File

```
$ emacs
M-x view-file RET <file>
```

### Windows

```
C:\> runemacs <file/dir>

gitbash$ runemacs <file/dir>

gitbash$ emacs <file/dir> &
```

## Save

```
C-x C-s
```

## Save As...

```
C-x C-w
```

## Quit

```
C-x C-c
```

## Undo/Redo

```
C-_
```

## Cancel Emacs Command Chain

```
C-g
```

## Next Search Result

```
C-s
```

## Toggle treating search pattern as literal vs regex

```
M-r
```

## Find and Replace

Find/Replace from cursor to end of file:

```
M-%
```

Wrap:

```
C-s
```

Enter text to find.
Enter text to replace.

`!` replaces all occurences.

`y` replace current match.

`n` skips over current match.

## Search a Directory

By default, Emacs offers grep for searching all files in a directory:

```
M-x rgrep
```

If Emacs has trouble finding the `grep` binary in Mac OS X, you can inform Mac apps of the full `PATH`:

https://gist.github.com/mcandre/7235205

## Fuzzy Find

The [fiplr](https://github.com/d11wtq/fiplr#fiplr---find-in-project-for-emacs) package offers a command for finding files in nested directories by typing any part of the filename.

## Regular Expressions

Emacs supports a regex syntax similar to PPCRE.

http://emacswiki.org/emacs/RegularExpression

## Select All

```
C-x h
```

## Cut

```
C-w
```

## Copy

```
M-w
```

## Paste

```
C-y
```

## Set mark

```
C-space
```

## Toggle Comment Marked Region

```
M-;
```

## Auto-Indent Current Line or Marked Region

```
TAB
```

## Insert literal Tab Character

```
C-q TAB
```

## Indent Marked Region Rigidly

```
M-x (indent-rigidly (region-beginning) (region-end) tab-width))

C-c >
```

## Outdent Marked Region Rigidly

```
M-x (indent-rigidly (region-beginning) (region-end (* tab-width -1))

C-c <
```

## Print buffer

```
M-x print-buffer
```

# Screens

## Windows

### Split Window Verticaly

```
C-x 2
```

## Split Window Horizontally

```
C-x 3
```

### Next Window

```
C-x o
```

### Close Window

```
C-x 0
```

### Grow Current Window

```
C-x ^
```

### Shrink Current Window

```
M-x shrink-window
```

Or switch windows and grow the other one.

## Buffers

### Create or Switch to Buffer

```
C-x b <name (default *scratch)>
```

### Set buffer mode

```
M-x <mode-name>
```

### Start of Buffer

```
M-<
```

### End of Buffer

```
M->
```

### Start of Line

```
C-a
```

### End of Line

```
C-e
```

### Page Up

```
M-v
```

### Page Down

```
C-v
```

### Delete

```
C-d
```

### Delete trailing whitespace

```
M-x delete-trailing-whitespace
```

### Final Newline preference

```
M-: (setq require-final-newline t)
M-: (setq require-final-newline nil)
```

User may need to delete and reinsert last character (e.g. `>` in `</html>`)
in order for preference to take effect.

### Cut Line

```
C-k
```

### Sort lines

1. Highlight relevant lines.
2. `M-x sort-lines`

# Help

## Variables

```
C-h v <name>
```

## Hotkeys

```
C-h k <key>
```

# IRC

## Launch IRC

```
M-x irc
```

## Join server

```
M-: (rcirc-connect server port nick
                   rcirc-default-user-name
                   rcirc-default-full-name
                   channels)
```

## Leave room

```
/part
```

# Alternatives

* [Nano](https://github.com/mcandre/cheatsheets/blob/master/nano.md) has a much easier learning curve than Emacs.
* [Vim](https://github.com/mcandre/cheatsheets/blob/master/vim.md) is comparable to Emacs in power, and offers shorter hotkeys for navigation and refactoring. Vim also tends to be installed by default on more systems.
