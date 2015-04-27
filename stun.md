# Stun Cheatsheet

Andrew Pennebaker

https://github.com/mcandre/cheatsheets/blob/master/stun.md

# About

Stun is a protocol for robustly querying network information such as IP addresses, even through NAT and proxies.

# Documentation

[Wikipedia: STUN](https://en.wikipedia.org/wiki/STUN)
[Public STUN server list](https://gist.github.com/mcandre/eb7c3e1fcd9541973ba8)

# Install

```
$ apt-get install stun

$ brew install stuntman
```

[stunserver_win32_1_2_5a.zip](http://www.stunprotocol.org/)

# Basic Usage

```
$ stunclient <stun-server>
```

Example:

```
$ stunclient stun.ekiga.net
stunclient stun.ekiga.net
Binding test: success
Local address: 192.168.100.121:56531
Mapped address: 107.48.201.7:56531
```

In other words, stunclient returns the internal IP address, as well as the external (global) IP address, of the host computer.

# Alternatives

* [ICanHazIP](http://icanhazip.com/)
* [ifconfig](http://man.cx/ifconfig) (Unix)
* [ipconfig](https://technet.microsoft.com/en-us/library/bb490921.aspx) (Windows)
