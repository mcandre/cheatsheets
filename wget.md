# wget Cheatsheet

Andrew Pennebaker

https://github.com/mcandre/cheatsheets/blob/master/wget.md

# About

GNU wget is a command line Web page downloader

# Documentation

[GNU wget manual](http://www.gnu.org/software/wget/manual/)

[man wget](http://linux.die.net/man/1/wget)

# Install

```
$ apt-get install wget

$ brew install wget

C:\> chocolatey install wget
```

[wget-1.11.4-1.msi](https://github.com/mcandre/wget-win)

# Configure

```
$HOME/.wgetrc
```

[Reference Dotfile](https://github.com/mcandre/dotfiles/blob/master/.wgetrc)

# Supported protocols

* HTTP
* HTTPS
* FTP

# Basic usage

## Download a Web page

```
$ wget http://www.google.com/index.html

$ less index.html
<!doctype html>...
```

## Handle special URL characters

```
$ wget "<URL>"
```

### Save as

```
$ wget -O <filename> <URL>
```

## Add a directory prefix

```
-P <name>
```

## Hide progress info

```
-q
```

## Output to STDOUT

```
$ wget -qO- <URL> | less
```

## Continue an interrupted download

```
$ wget [flags]
Control+C

$ wget -c [flags]
```

## Specify a user agent string

```
-U Firefox
```

# Crawling Websites

wget offers `-m` to *mirror* a website, downloading a local copy of each remote file.

```
$ wget -m http://www.gnu.org/software/wget/manual/
```

wget users often use `-mpNHk`, a bundle of several options, to intuitively crawl a website.

```
$ wget -mpNHk http://www.gnu.org/software/wget/manual/
```

## Traverse related domains

```
-H
```

## Specify allowed domains

```
-D .media.tumblr.com,media.tumblr.com,linuxinthewild.tumblr.com
```

## Wait between requests

```
-w <seconds>
```

## Convert links

wget can convert absolute links to local, so the mirror behaves as a more self-contained version of the original website.

```
-k
```

## Include related media files

```
-p
```

## Preserve timestamps

```
-N
```

## Save all files in the same directory

```
-nd
```

## Limit traversal to child and sister directories

```
-np
```

## Whitelist directory patterns

```
-I img/,meme/
```

## Blacklist directory patterns

```
-X thumbs/
```

## Whitelist file patterns

```
-A .html,.htm,.jpg,.jpeg,.gif,.png
```

## Blacklist file patterns

```
-R "*avatar*,*\?*,*_[0-9][0-9][0-9].*"
```

# Example scripts

[politerips](https://github.com/mcandre/politerips/tree/master/lib) offers example shell scripts for crawling websites with wget.

# Unofficial protocols

## HDFS

Instead of `hdfs://<host>:8020/<path>`, use:

```
$ wget http://<host>:50075/streamFile/<path>
```

## CouchDB

Instead of `couchdb://<authority>`, use:

```
$ wget http://<host>:5984/<authority>
```

# Alternatives

* [curl](https://github.com/mcandre/cheatsheets/blob/master/curl.md) outputs to STDOUT by default, making it a popular choice for debugging REST services.
* [lftp](https://github.com/mcandre/cheatsheets/blob/master/lftp.md) specializes in FTP transfers.
* [scp](http://linux.die.net/man/1/scp) specializes in SSH file transfers.
* [WWW::Mechanize](http://search.cpan.org/~ether/WWW-Mechanize-1.74/lib/WWW/Mechanize.pm) is a Perl library for fine-tuned Web crawling.
