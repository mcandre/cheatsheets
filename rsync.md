# Rsync Cheatsheet

Andrew Pennebaker

https://github.com/mcandre/cheatsheets/blob/master/rsync.md

# About

Rsync is a fast, fault-tolerant, file and folder synchronization system.

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

## Upload

```
$ rsync -a books me@mybookserver.com:/home/me/
```

## Download

```
$ rsync -a me@mybookserver.com:/home/me/books .
```

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

## Show overall progress bar

```
--info=progress2
```

Requires rsync 3.1.0+.

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

* [SSH](http://www.openssh.com/)
* [FTP](https://github.com/mcandre/cheatsheets/blob/master/lftp.md)
* [Git](https://github.com/mcandre/cheatsheets/blob/master/git.md)
