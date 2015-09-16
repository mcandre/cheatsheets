# tmux cheatsheet

Andrew Pennebaker

https://github.com/mcandre/cheatsheets/blob/master/tmux.md

# About

tmux is a program for managing multiple terminal sessions. Sessions can be created, destroyed, backgrounded, foregrounded, split, and logged.

# Documentation

* [Homepage](https://tmux.github.io/)
* [man tmux](http://www.openbsd.org/cgi-bin/man.cgi/OpenBSD-current/man1/tmux.1?query=tmux&sec=1)

# Install

```
$ apt-get install tmux

$ chocolatey install cygwin

$ brew install tmux
```

# Configure

```
$HOME/tmux.conf
```

## Tab completion for session names

See [tmux-completion](https://github.com/mcandre/tmux-completion)

# Hotkey Notation

* `C-` = `Control`
* `M-` = `Alt` ("Meta" key)
* `S-` = `Shift`
* `key-key key-key key-key...` = Hotkeys are pressed in order, not simultaneously.
* `<...>` = user-defined value
* `[...]` = optional

# Evaluate tmux Command

```
C-b : <command>
```

# Basic Commands

## Create new window

```
$ tmux [options]
tmux$
```

Options includes:

* `new -s <name>` Name the new session
* `-d` Automatically detach from the new window
* `-c <command>` Execute a shell command

## View session list

```
$ tmux ls
```

## Detach

Detaching a session allows it to run in the background, e.g. even after disconnecting from an SSH session.

```
C-b d
```

## Resume

tmux can resume a running session, e.g. once an SSH session has been reestablished.

```
$ tmux attach -t <name>
```

# Alternatives

* [screen](https://github.com/mcandre/cheatsheets/blob/master/screen.md)
