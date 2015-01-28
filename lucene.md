# Lucene Cheatsheet

Andrew Pennebaker

https://github.com/mcandre/cheatsheets/blob/master/lucene.md

# About

Lucene is a programmable search engine, used by [elasticsearch](http://www.elasticsearch.org/) and [Kibana](http://www.elasticsearch.org/overview/kibana/) to search public and private data collections.

# Documentation

[Apache Lucene](http://lucene.apache.org/)

[LuceneTutorial.com](http://www.lucenetutorial.com/lucene-query-syntax.html)

[Lucene in Action](http://www.amazon.com/dp/1933988177/)

# Basic queries

Lucene is case-insensitive.

```
cats

CATS

CaTs
```

Unlike other search engines, Lucene defaults term-paring to ORs rather than ANDs.

## Union

```
cats dogs

cats OR dogs
```

## Intersect

Remember to explicitly AND terms together:

```
cats AND dogs

+cats +dogs
```

## Nesting

```
(+cats +dogs) (+"peanut butter" +jelly)
```

## Subtraction

Minus (`-`) removes a term from results, and automatically ANDs it with the rest of the query.

```
cats -dogs
```

## Phrases

```
"grumpy cat"
```

### Wildcards

A question mark (`?`) matches a single, arbitrary character:

```
c?ts

+khtml +like +Geck?
```

An asterisk (`*`) will match anything in its position, though asterisks may require escaping (e.g. in phrases):

```
+"khtml, like" +Ge*

"\*, like Gecko"
```

# Operators

## Host-specific search

Hosts tend to require fully qualified domain names (`google` bad syntax, `google.com` good syntax). Though wildcards can help abbreviate this.

```
host:tomcat.apache.org

host:tomcat*
```

## Log file path

```
path:catalina*
```

## Custom attributes

Each Lucene index may specify additional query operators. Common operators include `message:` and `timestamp:`.

Note: When a term is not prefixed with an operator, it is automatically searched for across all operators. For best results, it is often useful to not specify *any* operators for your search terms.

# Alternatives

* [Google](https://github.com/mcandre/cheatsheets/blob/master/google.md)
* [DuckDuckGo](https://github.com/mcandre/cheatsheets/blob/master/duckduckgo.md)
* [Fetch](http://fetch.yellosoft.us/)
