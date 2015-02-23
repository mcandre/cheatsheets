# curl Cheatsheet

Andrew Pennebaker

https://github.com/mcandre/cheatsheets/blob/master/curl.md

# About

curl is a command line Web page downloader

# Documentation

[cURL Documentation](http://curl.haxx.se/docs/)

[man curl](http://man.cx/curl)

# Install

```
$ apt-get install curl

$ brew install curl

C:\> chocolatey install curl
```

# Configure

```
$HOME/.curlrc
```

[Reference Dotfile](https://github.com/necolas/dotfiles/blob/master/shell/curlrc)

# Supported protocols

* HTTP
* HTTPS
* FTP
* SFTP

# Basic usage

## Output to STDOUT

```
$ curl <URL> | less
```

## Save as

```
$ curl -o <filename> <URL>
```

## Specify a user agent string

```
-A Firefox
```

## Show HTTP Headers

```
-v
```

## Specify HTTP Method

```
-X POST
```

## Specify Content Type

```
-H "Content-Type: application/json
```

## Supply JSON Body

```
-d '{ ... }'
```

# Crawling Websites

See [curlmirror.pl](http://curl.haxx.se/programs/curlmirror.txt).

# Example scripts

* [nvm](https://github.com/creationix/nvm)
* [rvm](https://rvm.io/)
* [Homebrew](http://brew.sh/)

# Unofficial protocols

## HDFS

Instead of `hdfs://<host>:8020/<path>`, use:

```
$ curl http://<host>:50075/streamFile/<path>
```

## CouchDB

Instead of `couchdb://<authority>`, use:

```
$ curl http://<host>:5984/<authority>
```

# Alternatives

* [wget](https://github.com/mcandre/cheatsheets/blob/master/wget.md) specializes in webcrawling.
* [lftp](https://github.com/mcandre/cheatsheets/blob/master/lftp.md) specializes in FTP transfers.
* [scp](http://linux.die.net/man/1/scp) specializes in SSH file transfers.
* [WWW::Mechanize](http://search.cpan.org/~ether/WWW-Mechanize-1.74/lib/WWW/Mechanize.pm) is a Perl library for fine-tuned Web crawling.
