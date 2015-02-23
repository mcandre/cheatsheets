# wget Cheatsheet

Andrew Pennebaker

https://github.com/mcandre/cheatsheets/blob/master/wget.md

# About

GNU wget is a command line Web page downloader

# Documentation

[GNU wget manual](http://www.gnu.org/software/wget/manual/)

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

### Save as

```
$ wget -O <filename> <URL>
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
-U <string>
```

# Crawling Websites

wget can create a *mirror*, a local copy of a website.

```
$ wget -m http://www.gnu.org/software/wget/manual/
```

## Wait between requests

```
-w <seconds>
```

## Limit traversal to child and sister directories

```
-np | --no-parent
```

# Alternatives

* [curl](http://curl.haxx.se/) outputs to STDOUT by default, making it a popular choice for debugging REST services.
* [lftp](http://lftp.yar.ru/) specializes in FTP transfers.
* [WWW::Mechanize](http://search.cpan.org/~ether/WWW-Mechanize-1.74/lib/WWW/Mechanize.pm) is a Perl library for fine-tuned Web crawling.
