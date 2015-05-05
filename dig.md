# Dig Cheatsheet

Andrew Pennebaker

https://github.com/mcandre/cheatsheets/blob/master/dig.md

# About

Dig is a tool for querying DNS servers.

# Documentation

[man dig](http://man.cx/dig)

# Install

```
$ apt-get install dnsutils

C:\> chocolatey install dig
```

On Mac OS X, dig is built-in.

# Basic usage

```
$ dig [@<resolver>] <hostname> [options]
```

Examples:

```
$ dig www.google.com
...
www.google.com.		146	IN	A	173.194.192.147
www.google.com.		146	IN	A	173.194.192.104
www.google.com.		146	IN	A	173.194.192.99
www.google.com.		146	IN	A	173.194.192.105

;; Query time: 3 msec
;; SERVER: 192.168.2.1#53(192.168.2.1)
;; WHEN: Mon May  4 22:44:30 2015
;; MSG SIZE  rcvd: 128

$ dig @a.root-servers.net www.google.com | head
; <<>> DiG 9.8.3-P1 <<>> @a.root-servers.net www.google.com
; (1 server found)
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 37765
;; flags: qr rd; QUERY: 1, ANSWER: 0, AUTHORITY: 13, ADDITIONAL: 14
;; WARNING: recursion requested but not available

;; QUESTION SECTION:
```

## Summarize

```
dig www.google.com +short
173.194.192.103
173.194.192.106
```

## Reverse DNS

```
-x <IP address>
```

Examples:

```
$ dig -x 173.194.192.103 | tail
;103.192.194.173.in-addr.arpa.	IN	PTR

;; AUTHORITY SECTION:
194.173.in-addr.arpa.	60	IN	SOA	ns1.google.com. dns-admin.google.com. 92787525 21600 3600 1209600 10800

;; Query time: 3 msec
;; SERVER: 192.168.2.1#53(192.168.2.1)
;; WHEN: Mon May  4 23:02:22 2015
;; MSG SIZE  rcvd: 106
```

# Alternatives

* [nslookup](http://man.cx/nslookup)
* [whois](http://man.cx/whois)
