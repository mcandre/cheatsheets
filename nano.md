# Nano Cheatsheet

Andrew Pennebaker

https://github.com/mcandre/cheatsheets/blob/master/nano.md

## Documentation

[nano Command Manual](http://www.nano-editor.org/dist/v2.2/nano.html)

[Nano editor tutorials](http://www.debianadmin.com/nano-editor-tutorials.html)

[The Nano Text Editor](http://mintaka.sdsu.edu/reu/nano.html)

## Install

    $ apt-get install nano

    $ brew install nano

    C:\> chocolatey install nano

[nano-2.2.5.msi](http://www.yellosoft.us/helpers#nano)

## Configure

    ~/.nanorc

[Reference Dotfile](https://github.com/mcandre/dotfiles/blob/master/.nanorc)

Additional syntax highlighters:

[nano-highlight](https://github.com/serialhex/nano-highlight)

# Basic Commands

## Hotkey Notation

* `^` = `Control`
* `M-` = `Alt` ("Meta" key)

## Open File

    $ nano <file>

    $ nano
    ^R <file>

### Windows

    C:\> nano <file>

    gitbash$ nano <file>

## Save As...

    ^O

## Quit

    ^X

## Undo/Redo

    M-U

    M-E

## Cancel Nano Command

    ^C

## Next Search Result

    ^W

## Find and Replace

    ^\
    A

## Regular Expressions

    ^W
    M-R

    ^\
    M-R

## Cut

    ^K

## Copy

    M-6

## Paste

    ^U

## Set mark

    M-A

## Indent/Dedent Line or Marked Block Rigidly

    M-}

    M-{

## Auto-Indent Current Line or Marked Region

    TAB

## Start/End of File

    M-\

    M-/

## Start/End of Line

    ^A

    ^E

### Delete

    DEL

# Alternatives

* [Pico](http://www.washington.edu/pine/) is a precursor to Nano, often installed by default on Unix systems.
* [Emacs](https://github.com/mcandre/cheatsheets/blob/master/emacs.md) provides many more features than Nano.
* [Vim](https://github.com/mcandre/cheatsheets/blob/master/vim.md) also provides many more features than Nano.
