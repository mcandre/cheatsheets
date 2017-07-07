# Append text to a file

```
echo "Some appended text" >> <file>
```

# Prepend text to a file

```
echo "Some prepended text" | cat - <file> | tee <file>
```

# Clear Screen

```
Control+L
```

Note: The `Control+L` clear screen hotkey does not work in Command Prompt, where the `cls` command must be used instead. But the hotkey does work in Powershell, bash, and other more modern shells.
