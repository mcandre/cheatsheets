# GNU Screen cheatsheet

Andrew Pennebaker

https://github.com/mcandre/cheatsheets/blob/master/screen.md

# About

GNU Screen is a program for managing multiple terminal sessions as "windows". Windows can be created, destroyed, backgrounded, foregrounded, split, and logged.

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
$HOME/.screenrc
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
$ screen [options]
screen$
```

Options includes:

* `-S <name>` Name the new window
* `-d` Automatically detach from the new window
* `-X <command>` Execute a shell command

## Create new window from within screen:

```
screen$
C-a c

[C-a A <name>]
```

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
