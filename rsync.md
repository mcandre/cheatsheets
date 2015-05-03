# Rsync Cheatsheet

Andrew Pennebaker

https://github.com/mcandre/cheatsheets/blob/master/rsync.md

# About

Rsync is an efficient, fault-tolerant, file and folder synchronization system.

# Documentation

* [man rsync](http://man.cx/rsync)
* [RedHat Rsync Configuration Examples](https://access.redhat.com/documentation/en-US/Red_Hat_Enterprise_Linux/6/html/Managing_Confined_Services/sect-Managing_Confined_Services-rsync-Configuration_Examples.html)

# Install

```
$ apt-get install rsync

$ brew install rsync

C:\> chocolatey install rsync
```

# SSH Keys

Rsync encourages authentication with SSH keys, skipping the need for password authentication. Consult your [GitHub](https://help.github.com/articles/generating-ssh-keys/) or [GitLab](http://doc.gitlab.com/ce/ssh/ssh.html) documentation for more information on setting up SSH keys.

Like SSH, If SSH keys are not fully setup, rsync automatically downgrades to basic password authentication.

# Basic usage

```
$ rsync -a <source> <destination>
```

Where:

* `-a` means "synchronize all aspects of a file, including contents, name, permissions, and timestamp
* `<source>` and `<destination>` may be local file paths, SSH-compatible file paths, or a mix of both.

## Local machine copy

```
$ rsync -a books /mount/thumb-drive
```

`cp -r books books-backup` may be faster, but Rsync can resume a long or corrupted transfer, e.g. if a USB drive disconnects. Also, Rsync can show an overall progress bar, whereas `cp` with `pv` would only show a per-file progress bar.

## Show overall progress bar

```
--info=progress2
```

Requires rsync 3.1.0+.

## Upload

```
$ rsync -a books me@mybookserver.com:/home/me/
```

## Download

```
$ rsync -a me@mybookserver.com:/home/me/books .
```

## Pause

```
$ rsync -a books me@mybookserver.com:/home/me/
Control+C
```

Rsync is fault-tolerant, able to easily resume an interrupted transfer. So feel free to pause (kill) an Rsync transfer if you ever want to.

## Resume

If Rsync is interrupted, repeat the last command to continue the transfer.

```
$ rsync -a books me@mybookserver.com:/home/me/
<network disconnection occurs>
Control+C
<network connection restored>
$ rsync -a books me@mybookserver.com:/home/me/
$
```

# Service

## Configure

```
/etc/rsyncd.conf
```

Example:

https://raw.githubusercontent.com/seL4/isabelle/master/Admin/rsyncd.conf

## Start

```
$ sudo service rsync start

$ sudo /etc/init.d/rsync start

$ sudo rsync --daemon
```

## Stop

```
$ sudo service rsync stop

$ sudo /etc/init.d/rsync stop

$ sudo killall rsync
```

# Alternatives

* [cp -r](https://en.wikipedia.org/wiki/Cp_%28Unix%29) is faster for local files.
* [SSH](http://www.openssh.com/) is faster when interruptions are rare.
* [FTP](https://github.com/mcandre/cheatsheets/blob/master/lftp.md) can be faster, parallelizing individual file transfers.
* [Git](https://github.com/mcandre/cheatsheets/blob/master/git.md) and other version control systems offer file histories.
