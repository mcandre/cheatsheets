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
$ screen [-S <name>] [-X <command>]
screen$
```

Or, within screen:

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
screen$
C-a n
```

## Navigate to previous window

```
screen$
C-a p
```
