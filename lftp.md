# lftp Cheatsheet

Andrew Pennebaker

https://github.com/mcandre/cheatsheets/blob/master/lftp.md

# About

lftp is a command line FTP file transfer client.

# Documentation

[man lftp](http://lftp.yar.ru/lftp-man.html)

[LFTP Pocket Reference](http://mcandre.gitbooks.io/lftp-pocket-reference/)

# Install

```
$ apt-get install lftp

$ brew install lftp

C:\> chocolatey install lftp
```

[lftp-for-windows](http://nwgat.ninja/lftp-for-windows/)

# Configure

```
$HOME/.lftprc
```

[Reference Dotfile](https://github.com/mcandre/dotfiles/blob/master/.lftprc)

## Tab completion for bookmarks

See [lftp-completion](https://github.com/mcandre/lftp-completion)

# Supported protocols

* FTP
* SFTP
* FTPS
* FTPES
* FISH
* HFTP
* HTTP
* HTTPS

# Connect to server

```
$ lftp <URL>
```

# Create a bookmark

```
> bookmark <name>
```

# Connect to bookmarked server

```
$ lftp <name>
```

# Quit

```
> quit
```

Or

```
Control+D
```

# Change local directory

```
> lcd <local directory>
```

# View local directory

```
> lpwd
```

# Change remote directory

```
> cd
```

# View remote directory

```
> ls
```

# Update file listing

```
cache flush
```

# Download single file

```
> get <file>
```

# Download single file faster via parallel segments

```
> pget <file>
```

# Upload file

```
> put <file>
```

# Download directory

```
> mirror <remote directory>
```

# Upload directory

```
> mirror -R <local path> <remote path>
```

# Create directory

```
> mkdir
```

# Move file or directory

```
> mv <current filename> <new filename>
```

# Delete file or directory

```
> rm [-r] [-f] <file or directory>
```

```
> rmdir <directory>
```

# Alternatives

* [wget](https://github.com/mcandre/cheatsheets/blob/master/wget.md) specializes in webcrawling.
* [curl](https://github.com/mcandre/cheatsheets/blob/master/curl.md) outputs to STDOUT by default, making it a popular choice for debugging REST services.
* [scp](http://linux.die.net/man/1/scp) specializes in SSH file transfers.
* [WWW::Mechanize](http://search.cpan.org/~ether/WWW-Mechanize-1.74/lib/WWW/Mechanize.pm) is a Perl library for fine-tuned Web crawling.
