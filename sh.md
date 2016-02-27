# Append text to a file

```
echo "Some appended text" >> <file>
```

# Prepend text to a file

```
echo "Some prepended text" | cat - <file> | tee <file>
```
