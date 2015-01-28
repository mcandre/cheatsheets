# Google Cheatsheet

Andrew Pennebaker

https://github.com/mcandre/cheatsheets/blob/master/google.md

# About

Google is a flexible search engine.

# Documentation

[Punctuation, symboles & operators in search](https://support.google.com/websearch/answer/2466433?hl=en)

[Google Pocket Guide](http://www.amazon.com/dp/0596005504/)

# Basic queries

```
cats
```

## Intersect

```
cats AND dogs
```

## Union

```
cats OR dogs
```

## Nesting

```
(cats AND dogs) OR (peanut butter AND jelly)
```

## Subtraction

```
cats -dogs
```

## Phrases

```
"grumpy cat"
```

### Underscores

Underscores will search for literals as well as joined words:

```
quick_sort
```

will search for both `quick_sort` and `quicksort`.

### Wildcards

An asterisk (`*`) will match anything in its position:

```
a * saved is a * earned
```

# Operators

## File extensions

```
filetype:pdf programming
```

## Site-specific search

```
site:wikipedia.org music
```

## Pages that link to a URL

```
link:http://www.grumpycats.com/
```

## Related sites

```
related:github.com
```

## Display Google cached version of a page

```
cache:http://www.grumpycats.com/
```

# Alternatives

* [DuckDuckGo](https://duckduckgo.com/)
* [Lucene](http://lucene.apache.org/)
