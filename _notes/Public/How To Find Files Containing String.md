---
title : How To Find Files Containing String
feed: show
date : 30-08-2022
tags: powershell
---

Sometimes the need to find a string of text in one of the files can be troublesome, if you don't remember which files that string of text is in.

Using [Regex][1] and calling a search recursively on files, `Select-String` can be used to search each file for the resulting string using PowerShell.

```powershell
Get-ChildItem -Path . -Recurse -File | Select-String -Pattern '.*Search for this string.*'
```

Returns result with file path, line, and text matched:
```text
/path/to/file.txt:4:   Search for this string has been found
```

Here we can see the file is `/path/to/file.txt` the line matched was `4` and the string found matched the regex with the full string of text being `Search for this string has been found`.

[1]:https://regexr.com/ 'Regexr'