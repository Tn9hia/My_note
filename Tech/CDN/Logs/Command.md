Here is some useful command for log processing:

**wc** : count
- -l: number of lines
- -w: number of words
**grep**: find specify word
- -c : count matching lines
- -r : search recursive
```
grep -rnw "directory" -e "search-pattern"
```
**tail** : print tail of file
- -F: update realtime
**awk**: scripting language
```
awk '/search-pattern/ { action-to-take-on-matches; another-action; }' file-to-parse
```

sort:

uniq:

zcat: