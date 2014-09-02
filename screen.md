# GNU Screen cheatsheet

Andrew Pennebaker

https://github.com/mcandre/cheatsheets/blob/master/screen.md

# Documentation

http://www.gnu.org/software/screen/manual/

# Install

```
$ apt-get install screen

$ chocolatey install cygwin
```

In Mac OS X, GNU screen is a built-in program.

# Configure

```
~/.screenrc
```

# Hotkey Notation

* `C-` = `Control`
* `M-` = `Alt` ("Meta" key)
* `S-` = `Shift`
* `key-key key-key key-key...` = Hotkeys are pressed in order, not simultaneously.
* `<...>` = user-defined value
* `[...]` = optional

# Evaluate Screen Command

```
C-a : <command>
```

# Basic Commands

## Create new window

```
$ screen [-S <name> [-d]] [-X <command>]
screen$
```

Or, within screen:

```
screen$
C-a c

[C-a A <name>]
```

`screen -d ...` will automatically detach once the window is created.

## View screen list

```
C-a "
```

## Navigate to next window

```
C-a n
```

## Navigate to previous window

```
C-a p
```

## Detach

Detaching a window allows it to run in the background, e.g. even after disconnecting from an SSH session.

```
C-a d
```

## Resume

Screen can resume a running window, e.g. once an SSH session has been reestablished.

```
$ screen -x <name>
```
